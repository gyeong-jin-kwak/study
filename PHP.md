# PHP 공부하기

## 함수 (Function)
- 파일관리하기
  - is_file()
  - is_dir()
  - file_get_contents() : 파일의 내용을 읽는다
  - filt_put_contents()  
  
## 객체 (Object)
 - $abc = new SplFileObject('data.txt'); : 함수가 아닌 객체
  - $abc -> isFile();
  - $abc -> isDir();
  - $abc -> fread($abc -> fileSize())
  - $abc -> fwirte(ran(1, 100))
