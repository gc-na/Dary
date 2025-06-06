# [리눅스] C Shell (csh) cmp 사용법: 파일 비교

## Overview
`cmp` 명령어는 두 개의 파일을 비교하여 차이점을 찾아내는 데 사용됩니다. 이 명령어는 파일의 내용을 바이트 단위로 비교하며, 첫 번째로 다른 바이트의 위치를 출력합니다.

## Usage
기본 구문은 다음과 같습니다:
```csh
cmp [옵션] [인수]
```

## Common Options
- `-l`: 차이가 나는 바이트의 위치와 값을 출력합니다.
- `-s`: 파일이 동일한 경우 아무런 출력을 하지 않습니다.
- `-i <n>`: 비교를 시작할 바이트의 오프셋을 지정합니다.
- `-n <n>`: 비교할 바이트 수를 지정합니다.

## Common Examples
- 두 파일을 기본적으로 비교하기:
```csh
cmp file1.txt file2.txt
```
- 차이가 나는 바이트의 위치와 값을 출력하기:
```csh
cmp -l file1.txt file2.txt
```
- 파일이 동일한지 확인하기 (출력 없음):
```csh
cmp -s file1.txt file2.txt
```
- 특정 바이트부터 비교하기:
```csh
cmp -i 10 file1.txt file2.txt
```
- 처음 20바이트만 비교하기:
```csh
cmp -n 20 file1.txt file2.txt
```

## Tips
- `cmp` 명령어는 이진 파일을 비교할 때도 유용합니다.
- 결과를 다른 명령어와 함께 파이프하여 추가적인 처리를 할 수 있습니다.
- 파일의 크기가 클 경우, `-n` 옵션을 사용하여 필요한 부분만 비교하는 것이 효율적입니다.