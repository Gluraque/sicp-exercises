> (define (a-plus-abs-b a b)
    ((if (> b 0) + -) a b))
> (a-plus-abs-b -2 -3)
1
> (a-plus-abs-b -2 3)
1

Note: the entire if statement turns into either + or -
> (((if (> b 0) + -) a b)
            (+       a b))
