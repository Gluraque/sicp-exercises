< (define (cube-root x)
    (cube-root-iter 1.0 0 x))
> (define (cube-root-iter guess last-guess x)
    (if (good-enough? guess last-guess x)
        guess
        (cube-root-iter (improve-cube guess x)
                        guess
                        x)))
> (define (improve-cube guess x)
    (/ (+ (/ x(square guess))
           (* 2 guess))
       3))
> (cube-root 64)
4.000000000076121
> (cube-root 27)
3.0000000000000977

