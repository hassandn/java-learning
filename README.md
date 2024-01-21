 # java-learning

توی تابع های جاوا چیزی که برمیگردوننه رو قبلش مینویسن برای مثال

```
void method(){}

```
سطح دسترسی اون رو قبل از اون مشخص میکننن
```
public void method(){}
```
برای نام گداری کلاس ها باید از پاسکال کسی استفاده کنیم 
برای نام گذاری متد ها باید از کمل کیس استفاده کنیم
```
public Class Main{
  public void main(){
}
}
```
طریقه اجرا شدن جاوا به این صورت هست که ما میتونیم این کار ها رو انجام بدیم
فایل 
.java => compiler => .class => java runtime machine(java virtual machine) => run 
برای مشخص کردن متغیر ما از این استفاده میکنیم
```
int age = 20;
```

ما میتونیم از شورتکات ها استفاده کنیم برای مثال به جای انیکه کلی بنویسیم برای پرینت کردن میتونیم تایپ کنیم sout و تب رو بزنیم بقیشو خودش انجام میده   
یکی از فرق های رفرنس تایپ و پریمیتیو تایپ ها این هست که توی پریمیتیو وقتی مثلا میزنی x=y وای یک جای دیگه توی حافظه الوکیت میشه ولی وقتی دو تا شی رو اینکار انجام میدی به این صورت هست که هر دوشون به یک خونه اشاره میکنن
چجوری کاراکتر های خاص رو وارد کنیم؟
برای مثال فکر کن میخوام بگیم سلام فلانی و اسمش رو بزاریم بین دابل کوتیشن برای اینکار از بک اسلش استفاده میکنیم 
فرض کنید میخوایم ادرس رو بزاریم برای اینکار باید دوتا بک اسلش بزاریم 
```
 sout("hello \"hassan\"");
 addr = "C:\\home\\..";
\n -> next line
\t -> next line
```

```java
import java.awt.*;
// import java.lang.reflect.Array;
import java.util.Arrays;

public class Hello {
    public static void main(String[] args){
        int[] numbers = new int[5];
        numbers[0] = 1;
        numbers[1] = 2;
        numbers[2] = 3;
        numbers[3] = 4;
        numbers[4] = 5;
        
        // numbers = Arrays.toString(numbers);
        System.out.println(Arrays.toString(numbers));

    }

    
}
```
برای آرایه های چند بعدی داریم:
```
import java.awt.*;
import java.util.Arrays;

public class Hello {
    public static void main(String[] args){
        int[][] numbers = new int[2][3];
        numbers[0][1] =2;
        System.out.println(Arrays.deepToString(numbers));

    }

    
}
```
برای اینکه کانستنت بزاریم از کلمه کلیدی final استفاده میکنیم 
```
import java.awt.*;
import java.util.Arrays;

public class Hello {
    public static void main(String[] args){
        int result = 3*3;
        System.out.println(result);
        int x = 1;
        x++;
        ++x;
        System.out.println(x);
        int xx = 2;
        int y = ++xx;
        int z = xx++;
        System.out.println(y);
        System.out.println(z);
    }

    
}
```
implicit casting
byte > short > int > long > float > double
دیتا کانورت میشن 
 ما برای اینکه بتونیم با اعداد کار هایی رو انجام بدیم کتابخونه ای داریم به اسم NumberFormat مثلا برای اینکه مقدار پول بزنیم یا درصد بدست بیاریم 
برای گرفتن دیتا از کاربر ما میتونیم دستور زیر استفاده کنیم 



```
import java.text.NumberFormat;
import java.util.Locale;
import java.util.Scanner;

public class Hello {
    public static void main(String[] args){
        Scanner scanner  = new Scanner(System.in);
        System.out.print("write your name please =>");
        String userName = scanner.nextLine();
        System.out.print("write your age please =>");
        byte age = scanner.nextByte();
        System.out.println("hello "+ userName + " your age is "+ age);
    } 
}
```
