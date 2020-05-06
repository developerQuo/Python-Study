# Python-Study

* ### env : Python 3.8.2
* ### 파이썬의 특징
	+ 간결한 문법
		- 들여쓰기로 범위를 지정.
		- 변수 선언이 필요없다.
	+ OOP : 코드를 객체화 시킨
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
		- lst[:]를 사용하면 복사된 새로운 리스트 객체를 생성.
		- list는 문자열과 다르게 mutable하다. item을 바꿀 수 있다.
	<pre>
	lst = [2, 5.5, 'str']
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
	for i in range(1, 10):		# range(start, end, step)
		if i % 2 == 0:	# % is for modulo
			print("%d is even" % i)
		elif i % 3 == 0:
			print("%d is multiple of 3" %i)
		else:
			print("%d is odd" %i)
	else:	# for: loop가 다 돌았을 경우 실행된다. 단, break인 경우에는 실행되지 않는다.
		print("Wait!!")
	# while
	total = 0
	while total < 100:
		total += 1
	else:	# while: 조건이 false일 경우 실행된다. 단, break인 경우에는 실행되지 않는다.
		print("Wait!!")
	print(total)

	# list comprehension
	m = [i ** 2 for i in range(5)]
	print(m)</pre>

* ### 함수형 프로그래밍
	<pre>
	a, b = 0, 1	# 동시에 선언 가능. 변수에 값이 할당되기전에 우측에서 값이 먼저 정해진다. (우변에서는 좌에서 우로)
	while a < 10:	# 0이 아닌 정수 값은 true, 0인 정수 값은 false 이다. sequence의 길이가 0인 문자열이나 배열도 false 이다.
		print(a)	# 들여쓰기로 문법을 구분한다.
		a, b = b, a+b

	range(4)		# range()는 iterable이지만, list 객체가 아니다.
	>>> range(0, 4)
	list(range(4))	# list 객체로 반환하는 방법.
	>>> [0, 1, 2, 3]
	</pre>
	
	* pass 명령어는 클래스, 함수, 반복문에서 사용 가능하다.
	<pre>
	while True:
		pass
	class MyEmptyClass:
		pass
	def initlog(*arg):
		pass</pre>
	
	* def 정의 필요

	* parameter keyword 
		+ *args : 튜플 형태로 매개변수로 받아온다.
			- ','를 기준으로 원하는 만큼 매개변수를 넣어준다.
			- *[var1, var2, ...] 의 형태로 매개변수에 넣어준다.
		+ **kwargs : 딕셔너리 형태로 매개변수로 받아온다.
			- keyword = value의 형태로 매개변수에 넣어준다.
			- **{keyword : value)의 형태로 매개변수에 넣어준다.
		+ 매개변수 옵션 : 가독성과 성능을 위해 매개변수가 전달되는 방법 설정.
			- ex) def func(pos1, pos2, /, pos_or_kwd, *, kwd1, kwd2):
			- pos1, pos2 : Positional only (/ 키워드 앞까지)
				- 오직 매개변수 위치에만 영향을 받는다.
			- /: Positional or keyword	(/, *가 없다면 default)
			- *: Keyword only	(* 키워드 이 후부터)
		+ lambda expr : 산수를 간단하게 표현 가능.
		+ Documentation Strings : 함수의 __doc__ 기능
			- 첫 줄은 객체의 목적을 요약할 것.
			- 설명이 있다면 한 줄을 띄우고 단락별로 나눠서 적는다.
		+ Function Annotations : 사용자정의 함수의 데이터 타입을 저장하는 기능.
		<pre>
		def f(ham: str, eggs: str = 'eggs') -> str:
			print("Annotations:", f.__annotations__)
			print("Arguments:", ham, eggs)
			return ham + ' and ' + eggs

		f('spam')
		>>> Annotations: {'ham': <class 'str'>, 'eggs': <class 'str'>, 'return': <class 'str'>}
		>>> Arguments: spam eggs
		>>> 'spam and eggs'</pre>
		
		