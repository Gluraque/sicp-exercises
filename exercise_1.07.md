> (sqrt 0.000005)
0.031303263143156616
> (sqrt 1599999999999)
1264911.0640669563
> (define (sqrt x)
    (sqrt-iter 1.0 0 x))
> (define (sqrt-iter guess last-guess x)
    (if (good-enough? guess last-guess x)
        guess
        (sqrt-iter (improve guess x)
                   guess
                   x)))
> (define (good-enough? guess  last-guess x)
    (< (abs (- guess last-guess))(/ guess 100000)))
> (sqrt 0.000005)
0.0022360679774997903
> (sqrt 1599999999)
39999.999987829855

accuracy for very high and very low numbers greatly improved;
we introduced a new argument called last-guess which we use to check if the difference between the current guess and the last guess is less than the a tiny fraction of the current guess and if it is than we pass the function passes since we reached a precise enough result.
