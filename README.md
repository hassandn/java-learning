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
```
import java.text.NumberFormat;
import java.util.Locale;
import java.util.Scanner;

public class Hello {
    public static void main(String[] args){
        final byte monthOfYear = 12;
        final byte percent = 100;

        Scanner scanner = new Scanner(System.in);
        System.out.print("principle: ");
        int principle = scanner.nextInt();

        System.out.print("Annual Interest Rate: ");
        // float annualIntrestRate = scanner.nextFloat();
        float annualIntrestRate = Float.parseFloat(scanner.nextFloat());
        float monthlyIntrestRate = annualIntrestRate / percent / monthOfYear;

        System.out.print("Period(yearly): ");
        byte periodOfYear = scanner.nextByte();
        int peroidOfMonth = periodOfYear * monthOfYear;

        double montgage = principle * Math.pow(monthlyIntrestRate*(1+monthlyIntrestRate), peroidOfMonth) 
        /
        Math.pow((1+monthlyIntrestRate), peroidOfMonth)-1;
        String result =  NumberFormat.getCurrencyInstance().format(montgage);
        Locale englishLocale = new Locale("en", "US");
        NumberFormat result = NumberFormat.getCurrencyInstance(englishLocale);
        System.out.println("Montgage: "+result);


    } 
}

```
and توی جاوا به صورت زیر است && 
برای or || هست 
not is !
برای شرایط داریم
```
if(){
}
else if (){}
else
```
میتونی بعد از else if چیزی نزاری و باز هم کای میکنه این کد 
یک راه حل برای اینکه بهتر از if statement استفاده کنیم به صورت زیر هست فرض کن میخوایم با دونستن بالانس اکانت بانکی یک نفر بفهمیم که آیا بالانس خوبی داره یا نه 
```
import java.text.NumberFormat;
import java.util.Locale;
import java.util.Scanner;

public class Hello {
    public static void main(String[] args){
        int balance = 120_000;
        boolean hasGoodBalance;
        if (balance>100_000){
            hasGoodBalance = true;
        }
        else{
            hasGoodBalance = false;
        }
    } 
}
```
ی راه دیگه اینکه به صورت پیشفرض اون رو فالس بزاریم و اگه شرایط درست بود ترو بشه 
و یک شرایط دیگم داریم که ی استیتمنت بزاریم جلوی اون بولین که اگه درست بود ترو باشه اگرم غلط منفی
```
import java.text.NumberFormat;
import java.util.Locale;
import java.util.Scanner;

public class Hello {
    public static void main(String[] args){
        int balance = 120_000;
        boolean hasGoodBalance = (balance>100_000);
    } 
}

```
ی راه دیگه برای خلاصه کردن
مثلا فرض کن اگه شرایط برقرار بود میخوای که یک چیزی اساینمنت بشه به یک متغیر برای همیمن ما داریم :
مثلا میخوای که کاربر اگه بالانس اکانتش بالا تر از 100 هزار تا بود بره توی فرست کلاس اگه نه هم میره تو اکانومی برای اینکار ما میتونیم به روش خیلی ساده که اینطور هست پیش بریم 
```
import java.text.NumberFormat;
import java.util.Locale;
import java.util.Scanner;

public class Hello {
    public static void main(String[] args){
        int balance = 120_000;
        String useerClass;
        if (balance > 100_000){
            useerClass = "first";
        }
        else{
            useerClass = "economy";
        }
    } 
}
```
ولی راه بهتری که برای این وچود داره این هست :
```
import java.text.NumberFormat;
import java.util.Locale;
import java.util.Scanner;

public class Hello {
    public static void main(String[] args){
        int balance = 120_000;
        String useerClass = (balance>100_000) ? "first" : "economy";
    
    } 
}

```
اینجا میگه اگه شرط داخل پرانتز درست بود ما خواهیم داشت که ؟ و اگه غلط بود ما خواهیم داشت که : 

برای استفاده از 
```
import java.text.NumberFormat;
import java.util.Locale;
import java.util.Scanner;

public class Hello {
    public static void main(String[] args){
        String role = "admin";
        if (role == "admin"){
            System.out.println("you are an admin "+ role);
        }
        else if (role == "moderator"){
            System.out.println("you are a moderator");
        }
        else{
            System.out.println("you are ghuest");
        }


        switch (role) {
            case "admin":
                System.out.println("");
                break;  
            case "moderator":
                System.out.println("you are a moderator");
                break;

            default:
                System.out.println("you are ghuest");
                // break;
        }
    } 
}

```
اینم میشه استفاده از سوییچ کیس
```
import java.text.NumberFormat;
import java.util.Locale;
import java.util.Scanner;

public class Hello {
    public static void main(String[] args){
        Scanner scanner = new Scanner(System.in);
        System.out.print("print the number:");
        byte userChoice = scanner.nextByte();

        final boolean divisibleByThree = (userChoice % 3 ==0) ? true :false;
        final boolean divisibleByFive = (userChoice % 5 ==0) ? true : false;
        if (divisibleByFive && divisibleByThree){
            System.out.println("BuzzFizz");
        }
        else if (divisibleByFive){
            System.out.println("Buzz");
        }
        else if (divisibleByThree){
            System.out.println("Fizz");
        }
        else{
            System.out.println(userChoice);
        }

    } 
}

```
برای حلفه های for ما داریم 
```
import java.text.NumberFormat;
import java.util.Locale;
import java.util.Scanner;

public class Hello {
    public static void main(String[] args){
        for (int i = 10; i>5;i--){
            System.out.println("hello world "+ i);
        }

    } 
}
```
فرق while با for توی این هست که ما توی while نمیدونیم چقدر کار لازم داریم مثل وقتی که کاربر تا وقتی کوییت رو نزده کد باید کار کنه
```
import java.text.NumberFormat;
import java.util.Locale;
import java.util.Scanner;

public class Hello {
    public static void main(String[] args){
        Scanner scanner = new Scanner(System.in);
        String input ="";
        while (!input.equals("exit")) {
            input = scanner.next().toLowerCase();
            // String.format(null, input,args);  
            System.out.println(input);       
        }

    } 
}
```
ما do while هم داریم که حذاقل یک بار اجرا میشه 
چون اول انجام میده و در آخر شرط رو بررسی میکنه
```
import java.text.NumberFormat;
import java.util.Locale;
import java.util.Scanner;

public class Hello {
    public static void main(String[] args){
        Scanner scanner = new Scanner(System.in);
        String input ="";
        do {
            input = scanner.next().toLowerCase();
            // String.format(null, input,args);  
            System.out.println(input);   
        }
        while(!input.equals("exit"));
    } 
}
```
مثلا اینجا وقتی مینویسی exit exit رو مینویسه و اجراش تموم میشه
مبحث break , countinue
به این صورت هست که وقتی کد به بریک میخوره کنکل میکنه ادامه کار رو 
ولی وقتی کانتینیو میخوره برمیگرده و بقیه کد های بعدشو ایگنور میکنه و برمیگرده به اول حلقه

ما for each loop هم داریم 
```
public class Hello {
    public static void main(String[] args){
        String[] fruits = {"apple","orange","straeberry"};
        for (int i = 0; i<fruits.length;i++){
            System.out.println(fruits[i]);
        }
        for (String friut : fruits){
            System.out.println(friut);
        }
    }
}
```
فرقشون اینکه ما تو روش اول میونیم برعکس هم بخونیمشون و دترسی به ایندکس ها داشته باشیم ولی توی دومی فقط همینطوری اسم ها رو صدا میزنه 
```
import java.text.NumberFormat;
import java.util.Locale;
import java.util.Scanner;

public class Hello {
    public static void main(String[] args) {

        int principal = (int) getInputFromUser("Principle =>", 1_000, 1_000_000);
        float annualIntrest = (float) getInputFromUser("annualIntrest =>", 0, 30);
        byte years = (byte) getInputFromUser("Period(years) =>", 0, 30);

        String montgage = calculateMortgage(principal, annualIntrest, years);
        System.out.println("MONTGAGE \n________\nMontly Payment: "+montgage +"\nPAYMENT SCHEDULE\n_______________");
        paymentSchedule(180000, 1_822.41);
    }

    public static double getInputFromUser(String inputText, double min, double max) {
        Scanner scanner = new Scanner(System.in);
        scanner.useLocale(Locale.US);
        double value;
        while (true) {
            System.out.print(inputText);
            value = scanner.nextDouble();
            if (min < value && value <= max) {
                break;
            }
            System.out.print("value must be between " + min + " and " + max);
            continue;

        }
        return value;
    }

    public static String calculateMortgage(int principal, float annualIntrest, byte years) {
        final byte MONTHOFYEAR = 12;
        final byte PERCENT = 100;
        int numberOfPayments = years * MONTHOFYEAR;
        double monthlyInterest = (annualIntrest / PERCENT) / MONTHOFYEAR;
        double intermediate = 1 + monthlyInterest;
        double mortgage = principal * (monthlyInterest * Math.pow(intermediate, numberOfPayments))
                / (Math.pow(intermediate, numberOfPayments) - 1);

        String montgageCurrency = NumberFormat.getCurrencyInstance(Locale.US).format(mortgage);
        return montgageCurrency;
    }

    public static void paymentSchedule(int principal, double montgage){
        double principalSchedule = principal;
        while (principalSchedule != 0) {
            
            principalSchedule = principalSchedule - montgage;
            if (principalSchedule <=0){
                break;
            }
            System.out.println(NumberFormat.getCurrencyInstance(Locale.US).format(principalSchedule));

        }
    }
}

```
تمرینی که داد توی ویدیو ها 
برای اینکه برنامه ای رو نوشتیم رو برای کسی بفرستیم باید از جاوا استفاده کنیم 
توی قسمت java project میتونی جار فایل رو بگیری
برای ران کردنش هم توی ترمنیال اینو رو مینویسی
```
java -jar App.jar
```
# OOP
هر کلاسی state و behavor داره
کلاس یک بلو پرینت هست برای برنامه نویسی مثلا برای ماشین فیلد هایی که داریم برای استیتش ما خواهیم داشت که رنگش ریننگش ترمزش و متد هایی داریم به اسم تعویض چرخ
ما میتونیم هر چقدر که دلمون خواست از بلو پرینت ابجکت بسازیم
this توی متدها وقتی از این استفاده میکنیم میتونیم به فیلدمن درسترسی داشته باشیم  \
```
public class TextBox {
    public String text;//field

    public void setText(String text){
        this.text = text;
    }
    public void clear(){
        text = "";
    }

}
```
توی متد اول برای اینکه فیلدمون رو مشخص کنیم کدونه از دیس استفاده میکنیم ولی توی متد کلیر چون پارامتری نمیگیریم از دیس استفاده نمیکنیم چون معلومه با کدومشون کار دایرم 
توی جاوا باید هر کلاس رو توی یک فایل دیگه بسازیم که این بهمون کمک میکنه کدامون رو بهتر مرتب کنیم
