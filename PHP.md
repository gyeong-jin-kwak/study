# PHP 공부하기

## 함수 (Function)
+ 파일관리하기
  - is_file()
  - is_dir()
  - file_get_contents() : 파일의 내용을 읽는다
  - filt_put_contents()  
  
## 객체 (Object)
+ $abc = new SplFileObject('data.txt'); : 함수가 아닌 객체
  - $abc -> isFile();
  - $abc -> isDir();
  - $abc -> fread($abc -> fileSize())
  - $abc -> fwirte(ran(1, 100))
  
```
- SplFileObject : class
- $abc, $abc2 .. : instance
- isFile(), isDir() .. : method (function), behavior
- data.txt, data2.txt .. : state
- filename .. : instance variable, Instance Field, Instance Property
```
## 함수 스타일과 객체 스타일 비교해서 사용해보기
### 함수 (Function)
```
$adata = array('a', 'b', 'c');
array_push($adata, 'd');
foreach($adata as $item){
  echo $item. <br>
}
var_dump(count($adata));
```
### 객체 (Object)
```
$odata = new ArrayObject(array('a', 'b', 'c'));
$odata-> append('d');
foreach($odata as $item){
  echo $item. <br>
}
var_dump($odata->count());
```
## 클래스, 매소드, 인스턴스 만들기 
```
class MyFileObject {
  function isFile(){
    return is_file('data.txt');
  }
}

$file = new MyFileObject();
var_dump($file->isFile());
```
## 인스턴스 변수
$this -> 변수 를 통해서 data.txt와 같은 state에 접근할 수 있다.
```
class MyFileObject {
  function isFile(filename){
    return is_file($this -> filename)
  }
}

$file = new MyObjectFile();
$file -> filename = 'data.txt';
var_dump($file->isFile());
var_dump($file->filename); 
스테이트를 알 수 있다.
```
## Constructor
```
class MyObjectFile{
  function __construct($fname){
    $this->$filename = $fname;
  }
  function isFile(){
    return is_file($this->filename)
  }
}

$file = new MyObjectFile('data.txt');
var_dump($file->isFile());
var_duam($file->filename);
```
