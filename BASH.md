# Bash 스크립트
> 해당 문서는 4번의 Bash script 강좌에 대한 복습을 목표로 만들어졌습니다.
> 
> 매우 짧은 시간에 강좌가 진행된 관계로 보충 자료 및 연습해 볼 수 있는 자료로 제작할 예정 입니다.
>
> 시간이 되는데로 추가 예정 입니다.
>
>
# Bash Script 복습
> [기초] Linux(Bash)기초 명령어 활용

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

## 5. 스위치 구문:

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


## 6. 루프문(순환구조문): For -> Do -> Down, While -> Do -> done
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

## 7. 함수: 함수는 수학에서 함수를 만들듯 일정하게 반복되는 일을 함수로 만들어 두고, 해당 함수에 데이터를 넣으면 처리될 수 있게 하는 구조 입니다
- 함수 설정 방법 `function_name() { commands; }`.
- 함수 이름 설정정: `function_name`.
- Example:
  ```bash
  greet() {
      echo "Hello, $1!"
  }

  greet "KNIH"
  ```

## 8. 인수:
- 스크립트 제작 후 스크립트에 특정 파일 또는 명령을 지정해야할때 사용 합니다 using `$1`, `$2`, `$3`, etc. (for first, second, third argument, and so on).
- Example:
  ```bash
  echo "Script name: $0"
  echo "First argument: $1"
  echo "Second argument: $2"
  ```

## 9. 파일 존재 여부 :
- File existence check: `-e`, `-f`, `-d`, `-s`, `-r`, `-w`, `-x`,

 etc.
- 파일 조작 명령어 : `cp`, `mv`, `mkdir`, `rm`, `cat`, `ls`, etc.
- Example:
  ```bash
  # 파일 카피
  cp source_file destination_directory

  # 파일 이름 변경 또는 위치 변경(잘라내서 붙여 넣기)
  mv old_file new_location

  # 디렉토리 생성
  mkdir directory_name

  # 파일 또는 디렉토리 삭제
  rm file_or_directory

  # 파일 내부 보기 / 열기등등
  cat file_name

  # List files and directories
  ls
  ```

## 10. 조건문에 기반한 명령어 실행:
- 
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




# Bash Script 문제
[기초]
(1) ExampleData_Genetics\Fasta 폴더 내 PDE6B_PCR.fasta 를 cat으로 열어보세요

(2) 상기 연 파일의 전체 줄수를 구하세요

(3) "GGAGACGGTGTG" 가 속한 줄을 구하세요

(4) PDE6B_PCR.fasta 를 PDE6B_PCR.fa 로 한개 더 만드세요

(5) PDE6B_PCR.fa 를 gzip 으로 압축하세요

(6) 만들어진 PDE6B_PCR.fa.gz 를 zcat 으로 열어보세요

(7) 상기 PDE6B_PCR.fa.gz 파일의 전체 줄수를 구해보고 PDE6B_PCR.fasta 와 줄수가 같은지 비교해보세요 (파일 비교 기초)

(8) PDE6B_PCR.fa.gz 를 PDE6B_PCR.fasta.gz 로 변경해보세요

(9) ExampleData_Genetics\Fasta 내부 파일 리스트 및 용량을 filelist.txt 로 저장해보세요
[형식예시]
-rwxrwxrwx 1 hy hy   15 Mar  9  2024 USH2A_PCR.fasta.fai
-rwxrwxrwx 1 hy hy   15 Mar  9  2024 USH2A_PCR.fasta.fai
-rwxrwxrwx 1 hy hy   15 Mar  9  2024 USH2A_PCR.fasta.fai
-rwxrwxrwx 1 hy hy   15 Mar  9  2024 USH2A_PCR.fasta.fai

(10) 저장된 filelist.txt 에서 fai 문자열을 포함한 줄만 출력해보세요

(11) 폴더내 fasta로 끝나는 파일만 찾어 fasta.txt 로 저장합니다
[형식예시]
파일명.fasta
파일명.fasta

(12) 저장된 fasta.txt 내부에 있는 파일을 cat으로 전부 열어보세요

[응용]

(13) 상기 fasta.txt 파일 내부에 있는 파일 리스트를 for 문을 이용하여 출력하세요

(14) 제작된 for 문 중 파일리스트 출력이 성공 하였으면, 각 파일의 줄수를 출력해보세요

(16) 간단한 스크립트를 작성하여 "Hello, World!"를 출력하세요.
[예시] 
example.sh 를 제작 후 bash example.sh 로 했을시 "Hello, World!" 가 나오면 성공

(17) 사용자에게 변수를 입력받어 "Hello, [이름]!"이라고 출력하는 스크립트를 작성하세요

(18) PDE6B_PCR.fasta 파일의 줄수를 맨 왼쪽에 표기하세요
[awk 사용]
1 >ABCD
2 ATGCGGCCCCCGGCCCCCCCCC..
3 CCCCGGCCCCCGGCCCCCGGCC..


[유전체 분석(고급)]

(19) ExampleData_Genetics\Fastq 폴더 내 read1.fq.gz / read2.fq.gz 를 grch38 chr21.fa 를 다운 받어 bwa 로 mapping 후 haplotypecaller 로 gvcf 제작후 genotypeGVCFs 로 vcf 를 제작 하세요
래퍼런스는 https://ewels.github.io/AWS-iGenomes/ 사이트에서 입수하거나 기타 아는곳에서 입수하시면 됩니다.

(20) 상기 제작된 vcf 를 기반으로 rsid annotation 을 수행하세요



[REFERENCES]
1. (WSL의 설치) https://velog.io/@pikamon/Linux-3 
2. (매개변수) https://madnix.tistory.com/entry/%EC%95%84%EA%B7%9C%EB%A8%BC%ED%8A%B8argument-%EC%99%80-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0parameter-%EC%9D%98-%EC%B0%A8%EC%9D%B4
3. (리눅스 기초) https://github.com/zzsza/TIL/blob/master/Linux/1%EC%9E%A5.%EB%A6%AC%EB%88%85%EC%8A%A4-%EC%89%98%EA%B3%BC-%EB%AA%85%EB%A0%B9%EC%96%B4-%EA%B8%B0%EC%B4%88.md
4. (Bash Script) https://github.com/bobbyiliev/introduction-to-bash-scripting?tab=readme-ov-file
5. (Bash Script) https://www.hostinger.com/tutorials/bash-script-example
6. (Bash 기초) https://github.com/Gian77/Bash-For-Bioinformatics
7. (Bioinformatics_Bash) https://github.com/alexpiper/utility
8. https://ewels.github.io/AWS-iGenomes/
9. 


