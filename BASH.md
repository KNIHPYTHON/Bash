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
