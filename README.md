# Talentely Solution

# Conditional_Statement_Level_2 JAVA by Nitin Prajwal R

1. Check whether a triangle is Equilateral or Isosceles or Scalene based on its side

```jsx
import java.util.Scanner;

public class Main {

public static void main(String[] args) {

Scanner scanner = new Scanner(System.in);

int side1 = scanner.nextInt();

int side2 = scanner.nextInt();

int side3 = scanner.nextInt();

if (side1 == side2 && side2 == side3) {

System.out.println("Equilateral");

} else if (side1 == side2 || side2 == side3 || side3 == side1) {

System.out.println("Isosceles");
} else {

System.out.println("Scalene");

}
}
}
```

2. Input all angles of a Triangle and check whether it is "Valid" or "Not Valid"

```jsx
import java.util.Scanner;

public class Main {

public static void main(String[] args) {

Scanner scanner = new Scanner(System.in);

int angle1 = scanner.nextInt();

int angle2 = scanner.nextInt();

int angle3 = scanner.nextInt();

if ((angle1 + angle2 + angle3 == 180) && angle1 != 0 && angle2 != 0 && angle3 != 0) {

System.out.println("Valid");

} else {

System.out.println("Not Valid");

}

}

}
```

3. Find the minimum of 3 numbers

```jsx
import java.util.Scanner;

public class Main {

public static void main(String[] args) {

Scanner scanner = new Scanner(System.in);

long num1 = scanner.nextLong();

long num2 = scanner.nextLong();

long num3 = scanner.nextLong();

if (num1 < num2 && num1 < num3) {

System.out.printf("Minimum is %d", num1);

} else if (num2 < num1 && num2 < num3) {

System.out.printf("Minimum is %d", num2);

} else {

System.out.printf("Minimum is %d", num3);

}

}

}
```

4. Find maximum of 3 numbers

```jsx
import java.util.Scanner;

public class Main {

public static void main(String[] args) {

Scanner scanner = new Scanner(System.in);

long num1 = scanner.nextLong();

long num2 = scanner.nextLong();

long num3 = scanner.nextLong();

if (num1 > num2 && num1 > num3) {

System.out.printf("Maximum is %d", num1);

} else if (num2 > num1 && num2 > num3) {

System.out.printf("Maximum is %d", num2);

} else {

System.out.printf("Maximum is %d", num3);

}

}

}
```

5. Find the largest of 4numbers

```jsx
import java.util.Scanner;

public class Main {

public static void main(String[] args) {

Scanner scanner = new Scanner(System.in);

long n1 = scanner.nextLong();

long n2 = scanner.nextLong();

long n3 = scanner.nextLong();

long n4 = scanner.nextLong();

long max = (n1 > n2 ? n1 : n2) > (n3 > n4 ? n3 : n4) ? (n1 > n2 ? n1 : n2) : (n3 > n4 ? n3 : n4);

System.out.printf("Largest is %d", max);

}

}
```

6. Given 3 integer values, arrange those 3 values in ascending order using  macros

```jsx
import java.util.Scanner;

public class Main {

  public static void main(String[] args) {

      Scanner scanner = new Scanner(System.in);

      long num1 = scanner.nextLong();

      long num2 = scanner.nextLong();

      long num3 = scanner.nextLong();

      long max = Math.max(Math.max(num1, num2), num3);

      long min = Math.min(Math.min(num1, num2), num3);

      long mid = num1 + num2 + num3 - max - min;

      System.out.printf("%d < %d < %d", min, mid, max);

  }

}
```

---

7. Arrange the given 4  numbers in descending order

```jsx
import java.util.Scanner;

public class Main {

  public static void main(String[] args) {

      Scanner scanner = new Scanner(System.in);

      long n1 = scanner.nextLong();

      long n2 = scanner.nextLong();

      long n3 = scanner.nextLong();

      long n4 = scanner.nextLong();

      long max1 = Math.max(Math.max(n1, n2), Math.max(n3, n4));

      long min1 = Math.min(Math.min(n1, n2), Math.min(n3, n4));

      long min2 = Math.min(Math.max(n1, n2), Math.max(n3, n4));

      long max2 = Math.max(Math.min(n1, n2), Math.min(n3, n4));

      if (max2 < min2) {

long temp = max2;

max2 = min2;

min2 = temp;

}

System.out.printf("%d > %d > %d > %d", max1, max2, min2, min1);

}

}
```

---

8. Write a program to check whether the given time is valid or not

```jsx
import java.text.ParseException;

import java.text.SimpleDateFormat;

import java.util.Date;

import java.util.Scanner;

public class Main {

  public static void main(String[] args) {

      Scanner scanner = new Scanner(System.in);

      String input = scanner.nextLine();

      SimpleDateFormat sdf = new SimpleDateFormat("HH:mm:ss");

      sdf.setLenient(false);

      try {

          Date date = sdf.parse(input);

          int hours = Integer.parseInt(input.split(":")[0]);

          if (hours >= 0 && hours <= 24) {

System.out.println("Valid");

} else {

System.out.println("Not Valid");

}

} catch (ParseException | NumberFormatException e) {

System.out.println("Not Valid");

}

}

}
```

---

9. Write a program to input a given specific date and check whether the date is valid or not. Year will be in range 1900 to 9999

```jsx
import java.util.Scanner;

public class Main {

  public static void main(String[] args) {

      Scanner scanner = new Scanner(System.in);

      String input = scanner.nextLine();

      scanner.close();

      String[] parts = input.split("/");

      if (parts.length != 3) {

          System.out.println("Invalid date format");

          return;

      }

      int date = Integer.parseInt(parts[0]);

      int month = Integer.parseInt(parts[1]);

int year = Integer.parseInt(parts[2]);

if (isValidDate(date, month, year)) {

System.out.println("Valid");

} else {

System.out.println("Invalid");

}

}

public static boolean isValidDate(int date, int month, int year) {

if (date > 0 && date < 32 && month > 0 && month < 13 && year > 0 && year < 10000) {

if (date < 31 && (month == 4 || month == 6 || month == 9 || month == 11)) {

return true;

} else if (date < 32 && (month == 1 || month == 3 || month == 5 || month == 7 || month == 8 || month == 10 || month == 12)) {

return true;

} else if (month == 2) {

if ((date < 30 && ((year % 4 == 0 && year % 100 != 0) || (year % 400 == 0))) || (date < 29)) {

return true;

}

}

}

return false;

}

}
```