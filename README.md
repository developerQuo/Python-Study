# Python-Study
금융 파이썬!!

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
	text = 'this is a string object'</pre>

* ### 기본 자료구조
	: 객체를 담는 그릇.
	+ tuple: 0기반 인덱스. 불변.
	<pre>
	tp = (1, 3.5, 'string')</pre>
	+ list: 0기반 인덱스. 가변.
	<pre>
	lst = [2, 5.5, 'str']</pre>   
	** 튜플 <-> 리스트 변환 가능.
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
	