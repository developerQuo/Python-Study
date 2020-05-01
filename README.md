# Python-Study

* ### 파이썬의 특징
	+ 간결한 문법
		- 들여쓰기로 범위를 지정.
		- 변수 선언이 필요없다.
	+ OOP
	+ 인터프리터 방식 : 별도의 컴파일 과정이 필요없다.	
	+ 라이브러리와 모듈

* ### 인터프리터


* ### 기본 자료형
	: 동적 자료형. -> 코드를 실행할 때, 객체의 자료형이 결정된다.
	<-> 정적 자료형. -> 컴파일 이전에 이미 객체의 자료형이 결정된다.
	모든 것이 객체. -> 메소드를 가지고 있다.
	+ 정수: int형. 크기의 제한이 없다.
	<pre>
	a = 10</pre>
	+ 부동소수점: float형.
	<pre>
	a = 4.5</pre>
	+ 문자열: "", '', str함수로 정의 가능.
	<pre>
	text = 'this is a string object'
	
	print("""\	#\을 붙이면 \n이 생략되도록 할 수 있다.
		first line
		second line
	""")</pre>

	+ 문자열은 결합될 수 있다.
	<pre>
	3 * 'un' + 'ium'
	>>> 'unununium'

	# literals 간 결합은 가능하지만 변수나 표현식과 결합할 때는 '+' operator를 사용해야한다.
	word = 'Python'
	word + '!!'
	>>> Python!!
	(3 * 'un') + 'ium'
	>>> 'unununium'</pre>

	+ 문자열은 0부터 왼쪽으로 시작된다. 0은 항상 0이다.
	오른쪽에서 -1로 시작할 수도 있다.
	<pre>
	word[:2]
	>>> 'Py'</pre>

	+ 문자열은 immutable이다. 다른 문자열을 원할 경우, 새로 만들어야 한다.
	<pre>
	word[0] = 'B'	# 에러</pre>

* ### 기본 자료구조
	: 객체를 담는 그릇.
	+ tuple: 0기반 인덱스. 불변.
	<pre>
	tp = (1, 3.5, 'string')</pre>   
	** tuple <-> list 변환 가능.
	+ list: 0기반 인덱스. 가변.
	<pre>
	lst = [2, 5.5, 'str']</pre>   
		- lst[:]를 사용하면 복사된 새로운 리스트 객체를 생성.
		- list는 문자열과 다르게 mutable하다. item을 바꿀 수 있다.
		<pre>
		letters = ['a', 'b', 'c', 'd']
		letters[:2] = ['A', 'B']
		letters
		>>> ['A', 'B', 'c', 'd']
		letters[:] = []
		letters
		>>> []
		len(letters)
		>>> 0</pre>   
	+ dict
	+ set

* ### 제어구조
	: 
	+ 반복문, 제어문.
	<pre>
	# for, if
	for i in range(1, 10):
		if i % 2 == 0: # % is for modulo
			print "%d is even" % i
		elif i % 3 == 0:
			print "%d is multiple of 3" %i
		else:
			print "%d is odd" %i

	# while
	total = 0
	while total < 100:
		total += 1
	print total

	# list comprehension
	m = [i ** 2 for i in range(5)]
	print m</pre>

* ### 함수형 프로그래밍
	