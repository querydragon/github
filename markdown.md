# 줄바꿈
• 마크다운에서는 [Enter] 한번으로 개행 되지 않는다.

• 공백을 2번 입력해서 개행처리 가능

• [Enter] 두 번은 단락을 나누기

까망
하르방

까망  
포레스트

까망 포레스트

# 주석 Comment
<!-- 주석 내용 -->

# 글머리 1~6까지 지원
# H1
## H2
### H3
#### H4
##### H5
###### H6

# 인용 BlockQuote
중첩 블록이 가능하며, [Enter] 두 번 입력하면 분리할 수 있다.

> first blockqute
>> second blockqute
>>> third blockqute


# 순서 있는 목록
1. first.
2. second..
3. third...

# 순서없는 목록
• 글머리 기호: *, +, - 지원

• 공백 2칸으로 들여쓰기 한다.

+ 빨강  
  * 주황
  - 노랑  
    + 초록

# 인라인(Inline) 코드 블록
처음과 끝을 ` (back quote)으로 감싼다.

su 명령어  
`$ sudo su`

# 코드 블록
```
#include <stdio.h>
int main()
{
    printf("까망 하르방");
    return 0;
}
```

# 문법 강조(Syntax highlighting) 코드 블록
•  ```  다음에 강조하고 싶은 언어 종류 입력

• 다양한 언어가 지원된다.

  html / css / c / cpp / javascript 

  kotlin / sql / bash / java / json / shell 등

```cpp
#include <stdio.h>
int main()
{
    printf("까망 하르방");
    return 0;
}
```

# 수평선
***
까망
- - -
하르방
* * *

# 체크리스트 (Check List)
- [x] complete item
- [ ] incomplete item

# 글자 서식
*single asterisks 이텔릭체*  
_single underscores 이텔릭체_  

**double asterisks 볼드체**  
__double underscores 볼드체__  

***tripple underscores 볼드+이텔릭체***  
___tripple underscores 볼드+이텔릭체___  

~~cancelline 취소선~~  
**~~bold cancelline 볼드+취소선~~**  
<u>underline - 밑줄</u>

# 링크 생성
• [보여지는 글](링크 "설명")

• "설명"은 생략 가능하다.

• 링크 대신 파일 경로(Path)나 head 제목 활용 가능

[까망 포레스트](https://blackforest.tistory.com/ "일상 블로그")  
[까망 하르방](https://zoosso.tistory.com/ "기술블로그")

# 목차 생성
• [보여지는 글](#Head Name)

• 링크 작성시 공백은 하이픈(-)으로 연결

• 링크 부분은 소문자로 작성

• 클릭하면 해당 Head 위치로 가는 것을 확인할 수 있다.

[1번째](#1-headers-first)  
[2번째](#2-headers-두번째)  

# 1 headers first
## 2 headers 두번째

# 다른 파일 열기
아래와 같이 같은 경로에 [sw.md]와 [zzz.md]가 존재한다.
[zzz.md]에서 아래와 같이 작성하면

링크 클릭시 해당 파일이 열린다.

[sw 파일](./sw.md "목차 있는 파일")

# 이미지 파일 불러오기
• ![대체 텍스트](경로, "설명")

• 앞쪽에 느낌표(!)를 붙여준다.

• 지정한 경로에 파일이 없는 경우 대체 텍스트가 보인다.

• 설명은 생략 가능

![하늘 사진](./image/sky.jpg "DSR")  
![땅](./image/earth.jpg)

# 이미지에 링크 걸기
• [![대체 텍스트](이미지 경로, "설명")](URL 링크 "설명")

• [보여지는 글 = 이미지]가 되는 것이다.

# 상대참조 방식으로 링크 처리
• [보여지는 글자] [id]

  [id]: URL Link "optional comment"

• 재사용 시 유용하다.

[까망 포레스트][1]  
[까망 하르방][기술블로그]

[1]: https://blackforest.tistory.com/ "일상 블로그"
[기술블로그]: https://zoosso.tistory.com/

# 자동링크방지
URL 형식은 자동으로 링크처리되는데,
방지하고자 한다면 양쪽으로 ` (백틱)을 두어 인라인 코드로 만든다.

https://blackforest.tistory.com/
`https://blackforest.tistory.com/`

# 수식
• 처음과 뒤에 $ (달러 기호)로 감싼다.

• $$ 두 개씩 사용하면 가운데 정렬된다.

• 특수기호 문자하고 싶은 경우 \ (백슬러시)

$a^2 + b^2 = c^2$  
$x^2_1 + 2x_2 = 3$

$$(\alpha + \beta)^2 = \alpha^2 + 2\alpha\beta+\beta^2 $$

# 표 (Table)
• 제목 행 구분을 위해 -(hyphen/dash) 3개 필요

    :(Colons) 기호로 셀(열/칸) 안에 내용을 정렬할 수 있다.

• 같은 행에서 셀(열/칸) 구분은 |(vertical bar) 사용

    가장 좌/우측은 |(vertical bar) 기호 생략 가능

값 | 의미 | 기본값
---|:---:|---:
`static` | 유형(기준) 없음 / 배치 불가 | `static`
`relative` | 요소 **자신** 기준으로 배치 |
`absolute` | 위치 상 **_부모_(조상)요소** 기준으로 배치 |
`fixed` | **브라우저 창** 기준으로 배치 |


A (기본 왼쪽 정렬) | B (가운데 정렬) | C (오른쪽 정렬)
---|:---:|---:
`1` | 가나다라 | abc
`2` | 가나다라마 | abcd
`3` | 가나다라마바 | abcde
`4` | 가나다라마바사 | abcdef

# 마크다운이 HTML 문법을 모두 커버하지 않는다.
그렇기에 HTML과 CSS를 같이 활용하면 좋다.

 

토글 (Toggle)
<details open>
  <summary>열린 상태에서 시작</summary>
<pre>
내용 1
내용 2
내용 3
</pre>
</details>

<details>
  <summary>더보기</summary>
<pre>
내용 1
내용 2
내용 3
</pre>
</details>

글자색 및 하이라이트 처리
<mark>형광펜</mark>  
<span style="color:red">빨간</span>  
<span style="color:blue">파란</span>  
<span style="color:green">초록</span>  
<span style="color:yellow">노란</span>  
<span style="color:purple">보라</span>
