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
- isFile(), isDir() .. : method (function)
- data.txt, data2.txt .. : state
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
