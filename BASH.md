# Bash 스크립트 가이드

## 1. BASH 스크립트의 설정:
- sh로 확장자로 끝나게 설정  `.sh`  (e.g., `script.sh`).
- 스크립트 맨 윗 부분은 `#!/bin/bash`로 표기 -> 어떤 언어가 해당 파일을 실행 시킬지 결정
- chmod +x script.sh로 실행 파일로 변경(또는 bash script.sh 로 실행)

## 2. 변수설정 : 
- 변수 설정 방법: `variable_name=value`.
- 변수 사용 방법: `$variable_name`.
- 예시:
  ```bash
  name="KNIH"
  echo "Hello, $name!"
  ```

## 3. 입/출력 :
- 변수에 입력을 받는 방법: `read variable_name`.
- 변수를 출력하는 방법 `echo`: `echo "Hello, World!"`.
- 예시:
  ```bash
  echo "Enter your name:"
  read name
  echo "Hello, $name!"
  ```

## 4. 조건문: 조건이 있는 경우
- 사용법 `if`, `elif` (else if), and `else` 는 또 다른 조건에 따른 실행.
- 사용구문:
 ```bash
  if condition1; then
      # commands to execute if condition1 is true
  elif condition2; then
      # commands to execute if condition2 is true
  else
      # commands to execute if all conditions are false
  fi
  ```
- 비교문자: `==`, `!=`, `-eq`, `-ne`, `-lt`, `-gt`, `-le`, `-ge`, etc.
- 논리문자: `-a` (AND), `-o` (OR), `!` (NOT).
- 예시:
 ```bash
  echo "Enter a number:"
  read num
  if [ $num -eq 0 ]; then
      echo "Number is zero."
  elif [ $num -gt 0 ]; then
      echo "Number is positive."
  else
      echo "Number is negative."
  fi
  ```

## 6. 스위치 구문:

- Syntax
  ```bash
    echo "Enter a number:"
    read number
    case $number in
      1)
          echo "You entered number one."
          ;;
      2)
          echo "You entered number two."
          ;;
      3)
          echo "You entered number three."
          ;;
      *)
          echo "You entered an invalid number."
          ;;
    esac
  ```
  
 - The `$number` 해당 변수에 케이스에 따른 변수가 지정.
 - Each `1)`,`2)` 1,2,3,*(1,2,3 이외) 숫자가 변수에 지정될수 있음.
 - ;; 는 케이스별 문법(구문) 종료.
 - *) 는 Default 값으로 지정 된 문자가 없는 경우 지정 .


## 6. 루푸문(순환구조문):
- `for` loop:
  ```bash
  for item in list; do
      # commands to execute
  done
  ```
- `while` loop:
  ```bash
  while condition; do
      # commands to execute
  done
  ```
- `until` loop:
  ```bash
  until condition; do
      # commands to execute
  done
  ```
- Example:
  ```bash
  for i in 1 2 3; do
      echo $i
  done

## 7. Functions:
- Define a function using `function_name() { commands; }`.
- Call a function by its name: `function_name`.
- Example:
  ```bash
  greet() {
      echo "Hello, $1!"
  }

  greet "John"
  ```

## 8. Command Line Arguments:
- Access command-line arguments using `$1`, `$2`, `$3`, etc. (for first, second, third argument, and so on).
- Example:
  ```bash
  echo "Script name: $0"
  echo "First argument: $1"
  echo "Second argument: $2"


## 9. File Operations:
- File existence check: `-e`, `-f`, `-d`, `-s`, `-r`, `-w`, `-x`,

 etc.
- File manipulation commands: `cp`, `mv`, `mkdir`, `rm`, `cat`, `ls`, etc.
- Example:
  ```bash
  # Copy a file
  cp source_file destination_directory

  # Move a file
  mv old_file new_location

  # Create a directory
  mkdir directory_name

  # Remove a file or directory
  rm file_or_directory

  # Display the contents of a file
  cat file_name

  # List files and directories
  ls
  ```


## 10. Performing System Commands:
- System commands such as `shutdown`, `sleep`, `ps`, `grep`, etc., can be executed in a Bash script.
- Example:
  ```bash
  # Shutdown the system
  shutdown -h now

  # Pause the script execution for a specific duration
  sleep 5

  # List running processes
  ps aux

  # Search for a pattern in a file
  grep "pattern" file_name
  ```

## 11. Command Aliasing:
- Create aliases for frequently used commands using the `alias` command.
- Example:
  ```bash
  # Create an alias for the ls command
  alias ll='ls -alF'

  # Create an alias for the grep command
  alias cgrep='grep --color=auto'

  # Create an alias for a custom command
  alias mycommand='command_to_execute'
  ```

## 12. Performing Linux Commands on CLI Arguments Based on Conditions:
- Use conditional statements and command-line arguments to execute different commands based on conditions.
- Example:
  ```bash
  # Check if the first argument is "copy" and perform the copy operation
  if [ "$1" == "copy" ]; then
      cp "$2" "$3"
  fi

  # Check if the first argument is "move" and perform the move operation
  if [ "$1" == "move" ]; then
      mv "$2" "$3"
  fi
  ```



[Bash Script 과제]
> 해당 문서는 4번의 Bash script 강좌에 대한 복습을 목표로 만들어졌습니다.
> 
> 매우 짧은 시간에 강좌가 진행된 관계로 보충 자료 및 연습해 볼 수 있는 자료로 제작할 예정 입니다.
>
> 시간이 되는데로 추가 예정 입니다. 

- [기초] Linux(Bash)기초 명령어 활용

(1) 기본 커맨드






- [중급] Bash 





- [고급] Bash Script 의 작성 및 실행







-






[REFERENCES]
1. https://velog.io/@pikamon/Linux-3 (WSL의 설치)

```
public class BootSpringBootApplication {
  public static void main(String[] args) {
    System.out.println("Hello, Honeymon");
  }
}
```
