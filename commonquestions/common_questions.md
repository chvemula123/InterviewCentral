 Common Programming Questions
--------------------------------------------------------------------------------------------------------
1) **Write a simple Java program which will print Fibonacci series e.g. 1 1 2 3 5 8 13 ... . up to a given number.**

````java
  public static void main(String[] args) {
        //Get user Input for number of the fibonacci numbers to print.
       System.out.println("Enter number upto which Fibonacci series to print: ");
       int seriesNumber = new Scanner(System.in).nextInt();

       System.out.println("Fibonacci series upto " + seriesNumber +" numbers : ");

       //Go thru the series until each number is calculated
       for(int i = 1; i<= seriesNumber; i++){
           System.out.print(calculateFibonacciRecursive(i) + " ");
       }
    }

    public static int calculateFibonacciLoop(int n) {
        if (n == 1 || n == 2) {
            return 1;
        }
        int fib1 = 1, fib2 = 1, fibonacci = 0;

        for (int i = 3; i <= n; i++) {
            fibonacci = fib1 + fib2;
            fib1 = fib2;
            fib2 = fibonacci;
        }

        return fibonacci;
    }


    public static int calculateFibonacciRecursive(int n) {
        if (n == 1 || n == 2) {
            return 1;
        }
        return calculateFibonacciRecursive(n - 1) + calculateFibonacciRecursive(n - 2);
    }
````