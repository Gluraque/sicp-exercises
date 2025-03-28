> (define (new-if predicate
                  then-clause
                  else-clause)
    
    (cond (predicate then-clause)
          (else else-clause)))
> (new-if (= 2 3) 0 5)
5
> (new-if (= 1 1) 0 5)
0
> (define (sqrt-iter guess x)
    (new-if (good-enough? guess x)
            guess
            (sqrt-iter (improve guess x) x)))
sqrt-iter will never terminate. since Scheme uses applicative order evaluation so another sqrt-iter will be evaluated resulting in another new-if resulting in another sqrt-iter
