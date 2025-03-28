> (define (p) (p))
> (define (test x y)
    (if (= x 0)
        0
        y))
> (test 0 (p)) //This is an infinite loop, because if x = 0 we call y and our y is p which calls p again which then repeats

Applicative-Order Evaluation:
both arguments to a function are evaluated before the function body itself is evaluated, so in this example (test 0 (p)) it would check x which is 0 and can be evaluated very quickly, it then evaluates y which is (p), since (p) calls itself recursively without any base case it will lead to an infinite recursion and wont terminate (it will look like the program loads forever)

Normal-Order Evaluation:
now here it will look at the first argument x and then look at the function body and see that it is 0 which returns 0 and it will immediatly return 0, the way in which it is different is that it will skip the second argument y since it already looked at the function body before evaluating y and found a successful result, thus bypassing the infinite loop and thus also being able to return 0;

I am using racket for these exercises and this exercise proved that racket uses Applicative-Order Evaluation, since when i tried to run this test i got stuck in an infinite loop.
