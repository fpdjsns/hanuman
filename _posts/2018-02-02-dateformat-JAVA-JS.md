---
title : JAVA DATE형 JAVASCRIPT DATE형으로 변형
layout: post
---

```Mon Jan 29 17:48:51 KST 2018```  
이런 식으로 생긴 자바 Date형이 들어가는 객체의 리스트를 클라이언트 측에서 받아서  
```2018-01-29 17:48```  
와 같이 *YYYY-MM-DD HH:mm* 식으로 출력하고 싶었습니다.  
자바 Date형이 저런식으로 문자열로 들어왔기 때문에 임의의 가공이 필요했고 함수를 만들어서 해결하였습니다.  

```javascript
// Specifies a non-ISO Long date.
document.writeln((new Date("2010 June 9")).toUTCString());
```
javascript에서 위와 같은 입력으로 Date형의 생성자를 이용할 수 있다는 것을 알게되고 이를 응용하여 함수를 만들었습니다.  


```javascript
var changeDateFormat = function(originalDate) {
  var javaDateList = originalDate.split(' ');
  var jsDate = new Date(javaDateList[1] + " " + javaDateList[2] + " " + javaDateList[5] + " " + javaDateList[3])
  return jsDate;
}
```

위 changeDateFormat는 파라미터로 JAVA Date형을 받고 이를 JAVASCRIPT로 쉽게 가공할 수 있는 JAVASCRIPT Date형으로 변형하는 함수입니다. 

Date의 생성자의 파라미터로는 **Jan 29 2018 17:48:51** 와 같은 형식이 들어갑니다.

```javascript
console.log(javaDate);
jsDate = changeDateFormat(javaDate);
console.log(jsDate);
```
> Mon Jan 29 17:48:51 KST 2018   
>->  Mon Jan 29 2018 17:48:51 GMT+0900 (대한민국 표준시)

변환 후와 변환 뒤에 console.log로 결과를 찍어보면 위와 같은 변화가 있는 것을 볼 수 있습니다.

보기에는 달라진게 별로없지만 자료형이 문자열에서 javascript에서 **가공할 수 있는** DATE형식으로 변경되었습니다.


참고 : <https://msdn.microsoft.com/ko-kr/library/ff743760(v=vs.94).aspx>
