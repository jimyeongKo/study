#add
박찬호 선수가 총 3번의 투구를 138, 129, 142(km) 의 속도록 던졌다면 다음과 같이 코드를 작성할 수 있다.

ArrayList pitches = new ArrayList();<br>
pitches.add("138");<br>
pitches.add("129");<br>
pitches.add("142");<br>
add 라는 메소드를 이용하여 투구 스피드를 저장했다.

만약 첫번째 위치에 "133"이라는 투구 스피드를 삽입하고 싶다면 아래와 같이 코딩하면 된다.

pitches.add(0, "133");    // 첫번째 위치에 133 삽입.<br>
만약 2번 째 위치에 133을 삽일 할 경우에는 다음과 같이 코딩하면 된다.

pitches.add(1, "133");<br>
※ 자바는 J2SE 5.0 버전 이후부터 ArrayList<String> pitches = new ArrayList<String>(); 
<br>이런식으로 객체를 포함하는 자료형도 어떤 객체를 포함하는지에 대해서 명확하게 표현하는것을 권고하고 있다. 이클립스에서 위와 같이 코딩하면 명확한 타입을 명시하라는 warning이 표시될 것이다. 이 부분에 대한 자세한 내용은 다음 장인 제네릭스에서 자세하게 설명한다.
<br>
<br>
get
박찬호 선수의 2번째 투구 스피드를 알고 싶다면 다음과 같이 하면 된다.

System.out.println(pitches.get(1));<br>
ArrayList의 get 메소드를 이용하면 특정 인덱스의 값을 추출할 수 있다.

#size
size 메소드는 ArrayList의 갯수를 리턴한다.

System.out.println(pitches.size());<br>
현재 pitches에 담긴 갯수에 해당되는 값이 출력될 것이다.

#contains
contains 메소드는 리스트 안에 항목값이 있는지를 판별하여 그 결과를 boolean으로 리턴한다.

System.out.println(pitches.contains("142"));<br>
142라는 값을 포함하고 있으므로 true가 출력될 것이다.

#remove
remove 메소드에는 2개의 방식이 있다. (이름은 같지만 입력파라미터가 다르다)

remove(객체)<br>
remove(인덱스)<br>
remove(객체)의 경우는 리스트에서 객체에 해당되는 항목을 삭제하고 삭제한 결과를 리턴한다.

System.out.println(pitches.remove("129"));<br>
수행결과는 다음과 같다.

true
"129"라는 항목이 성공적으로 삭제되고 true를 리턴한다.

remove(인덱스)의 경우는 해당 인덱스의 항목을 삭제하고 삭제된 항목을 리턴한다.

System.out.println(pitches.remove(0));<br>
수행결과는 다음과 같다.

138
pitches의 첫번째 항목은 "138"이므로 "138"이 삭제된 후 "138"을 리턴했다.


#배열이란
같은 탑의 변수들을 하나로 묶어서 저장하는 것
배열은 같은 타입의 변수들을 연속된 공간에 저장하는 것을 말한다.

1. 배열 선언하기

배열을 생성하기 위해선 먼저 선언을 해주어야 합니다. 배열을 선언하는 방법은 두 가지가 있습니다.

선언할 때 대괄호 [ ]를 변수 타입 뒤에 붙이거나 변수 이름 뒤에 붙이면 됩니다.


2. 배열 생성하기

배열 선언이 완료되었으니 이제 배열 생성하는 법을 알아볼까요?

배열을 생성한다는 의미는 실제로 값을 저장할 수 있는 공간이 만들어졌다는 것입니다.
여기서 중요한 포인트는 배열을 생성하기 위해 'new'와 함께 타입과 길이를 설정해야 합니다.

#제네릭스 (Generics)

제네릭스(Generics)는 자바 J2SE 5.0 이후에 도입된 개념이다.

여기서는 제네릭스를 사용하는 방법에 대해서만 다룬다. 제네릭스를 만드는 방법은 입문서에 어울리지 않는 고급 주제이므로 이 책에서는 생략한다.

다음과 같은 것이 제네릭스이다.

ArrayList<String> aList = new ArrayList<String>();<br>
제네릭스가 도입되기 전인 J2SE 1.4 까지는 위의 코드를 다음과 같이 사용했다.

ArrayList aList = new ArrayList();<br>
두 개 코드의 차이점은 ArrayList 라는 자료형 타입 바로 옆에 <String> 과 같은 문구가 있느냐 없느냐의 차이이다.
제네릭스로 자료형을 선언하기만 하면 그 이후로는 자료형에 대한 형변환 과정이 필요없다. 이미 컴파일러가 aList 에는 반드시 String 자료형만 추가 되어야 함을 알기 때문이다.
이렇게 제네릭스를 이용하면 형변환에 의한 불필요한 코딩, 잘못된 형변환에 의한 런타임 오류등에서 벗어날 수 있게 된다.

#MAP
Map은 리스트나 배열처럼 순차적으로(sequential) 해당 요소 값을 구하지 않고 key를 통해 value를 얻는다.
맵(Map)의 가장 큰 특징이라면 key로 value를 얻어낸다는 점이다.
baseball이란 단어의 뜻을 찾기 위해서 사전의 내용을 순차적으로 모두 검색하는 것이 아니라 baseball이라는 단어가 있는 곳만을 펼쳐보는 것이다.

#put
자바의 맵(Map)중 가장 간단한 HashMap에 대해서 알아보자.

HashMap<String, String> map = new HashMap<String, String>();
map.put("people", "사람");
map.put("baseball", "야구");
key와 value가 String 형태인 HashMap을 만들고 위에서 보았던 예제의 항목값들을 입력해 보았다.
key와 value는 위 예제에서 보듯이 put메소드를 이용하여 입력한다.
※ HashMap 역시 제네릭스를 이용한다. 위의 HashMap 의 제네릭스는 Key, Value 모두 String 타입이다

#get
key에 해당되는 value값을 얻기 위해서는 다음과 같이 한다.

System.out.println(map.get("people"));<br>
위와같이 get 메소드를 이용하면 value값을 얻을 수 있다. 위 예제는 결과로 "사람"이라는 문자열을 출력할 것이다.

#containsKey
containsKey 메소드는 맵(Map)에 해당 키(key)가 있는지를 조사하여 그 결과값을 리턴한다.

System.out.println(map.containsKey("people"));
<br>"people"이라는 키는 존재하므로 true가 출력될 것이다.

#remove
remove 메소드는 맵(Map)의 항목을 삭제하는 메소드로 key값에 해당되는 아이템(key, value)을 삭제한 후 그 value 값을 리턴한다.

System.out.println(map.remove("people"));<br>
"people"에 해당되는 아이템(people:사람)이 삭제된 후 "사람"이 출력될 것이다.

#size
size 메소드는 Map의 갯수를 리턴한다.

System.out.println(map.size());
<br>"people", "baseball" 두 값을 가지고 있다가 "people"항목이 삭제되었으므로 1이 출력될 것이다.

다음은 테스트 시 사용되었던 코드 전체이다.

TestMap.java

import java.util.HashMap;

public class TestMap {<br>
    public static void main(String[] args) {<br>
        HashMap<String, String> map = new HashMap<String, String>();<br>
        map.put("people", "사람");<br>
        map.put("baseball", "야구");<br>

        System.out.println(map.get("people"));
        System.out.println(map.containsKey("people"));
        System.out.println(map.remove("people"));
        System.out.println(map.size());
    
    }
}
<br>LinkedHashMap과 TreeMap

Map의 가장 큰 특징은 순서에 의존하지 않고 key로 value를 가져오는데 있다.
하지만 가끔은 Map에 입력된 순서대로 데이터를 가져오고 싶은 경우도 있고 때로는 입력된 key에 의해 소트된 데이터를 가져오고 싶을 수도 있을 것이다.
이런경우에는 LinkedHashMap과 TreeMap을 사용하는 것이 유리하다.

LinkedHashMap은 입력된 순서대로 데이터가 출력되는 특징을 가지고 있다.
TreeMap은 입력된 key의 소트순으로 데이터가 출력되는 특징을 가지고 있다.

메소드는 클래스 내에 구현된 함수를 의미하는데 보통 함수라고 말하지 않고 메소드라고 말한다.

#private
접근제어자가 private으로 설정되었다면 private 이 붙은 변수, 메소드는 해당 클래스에서만 접근이 가능하다.

#default
접근제어자를 별도로 설정하지 않는다면 접근제어자가 없는 변수, 메소드는 default 접근제어자가 되어 해당 패키지 내에서만 접근이 가능하다.

#protected
접근제어자가 protected로 설정되었다면 protected가 붙은 변수, 메소드는 동일 패키지내의 클래스 또는 해당 클래스를 상속받은 외부 패키지의 클래스에서 접근이 가능하다.

#public
접근제어자가 public으로 설정되었다면 public 접근제어자가 붙은 변수, 메소드는 어떤 클래스에서라도 접근이 가능하다.

#정적 변수와 메소드 (static)
static은 보통 변수나 메소드 앞에 static 키워드를 붙여서 사용하게 된다.
static 키워드를 붙이면 자바는 메모리 할당을 딱 한번만 하게 되어 메모리 사용에 이점을 볼 수 있게된다.