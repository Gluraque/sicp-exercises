> (define (square x) (* x x))
> (square 5)
25
> (define (sum-larger-squares a b c)
      (cond ((and (<= a b)(<= a c)) (+ (square b)(square c)))
            ((and (<= b a)(<= b c)) (+ (square a)(square c)))
            (else (+(square a)(square b)))))
> (sum-larger-squares 1 2 3)
13
> (sum-larger-squares 3 2 1)
13
> (sum-larger-squares 3 1 2)
13
