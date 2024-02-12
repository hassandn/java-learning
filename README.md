 # java-learning

توی تابع های جاوا چیزی که برمیگردوننه رو قبلش مینویسن برای مثال

```java
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
توی جاوا باید هر کلاس رو توی یک فایل دیگه بسازیم که این بهمون کمک میکنه کدامون رو بهتر مرتبکنیم
خب حالا فرض کن که ما تکست رو هیچی مقدار بهش ندادیم مشکل اینجا شروع میشه که وقتی خواستیم مثلا خروجی رو آپرکیس نشون بدیم چون Null برمیگردونه به مشکل برخواهیم خورد 
برای اینکه به این مشکل برنخوریم بهش یک مقدار دیفالت میدیم 
```
package com.hassandn;

public class Main {
    public static void main(String[] args) {
        var txt1 = new TextBox();
        txt1.setText("hassandn");
//        System.out.print(txt1.text);

        var txt2 = new TextBox();
        txt2.setText("hassandn");
        

    }
}


```
میتونستیم به حای var از TextBox استفاده کنیم که البته استفاده از این باعث میشه که آدم گیج بشه برای همین از var استفاده میکنن
جاوا گاربیج کالکتور داره مبحث الوکیتش اینطوری هست که ما یکی stack داریم و یکی heap داره توی رفرنس تایپ ها اصله متغیر توی هیپ هستن و پوینترشون توی استک هست 
وقتی دوتا پیونتر به یک خونه ارجاع داشته باشن خوده جاوا این قضیه رو هندل میکنه که که مشکلاتی مثل ارجاع معلق پیش نیان
```
package com.hassandn;

public class Main {
    public static void main(String[] args) {
        int baseSalary = 50_000;
        int hourlyRate = 20;
        int extraHour  = 10;
        int wage = calculateSalary(baseSalary,hourlyRate,extraHour);
        System.out.println(wage);
    }
    public static int calculateSalary(int baseSalary, int hourlyRate, int extraHour){
        int result = baseSalary + (hourlyRate * extraHour);
        return  result;
    }
}
```
به کد بالا میگن کده procedual یا رویه ای بعنی برای هر کار متد صدا بزنیم و هی بهشون پارامتر بدیم 
## encapsulation
Bundle the data and methods that operate on the data in a sigle unit.
```
package com.hassandn;

public class Employee {
    public int baseSalary ;
    public int hourlyRate ;
    public int extraHour   ;

    public int calculateSalary(int extraHour){
        int result = baseSalary + (hourlyRate * extraHour);
        return  result;
    }
}

```
توی این کد کلاس امیپلوی رو داریم دلیل اینکه اکسترا اور رو گرفتیم برای این هست که ساعات هر بار فرق خواهند کرد 
و این هم کد مین ما هست 
```
package com.hassandn;

public class Main {
    public static void main(String[] args) {

        var employee = new Employee();
        employee.baseSalary = 60_000;
        employee.hourlyRate = 60;
        int wage = employee.calculateSalary(15);
        System.out.println(wage);

    }

}
```
## getters and setters
خب اینجا یک مشکل داریم چون الان ما میتونیم مستقیم بیس سلری رو عوض کنیم و یک نکته دیگم هست که ما الان نمیتونیم ولیدت کنیم برای همین ما از getters and setters استفاده میکنیم 
برای مثال کد های بالا که اصلاح شدن به صورت زیر هستن
```
package com.hassandn;

public class Employee {
    private int baseSalary ;
    private int hourlyRate ;
    public int extraHour   ;

    public int calculateSalary(int extraHour){
        int result = baseSalary + (hourlyRate * extraHour);
        return  result;
    }
    public void setBaseSalary(int baseSalary){
        if (baseSalary<=0)
            throw new IllegalArgumentException("Salary Must be a positive number.");
        this.baseSalary = baseSalary;
    }

    public int getBaseSalary(){
        return baseSalary;
    }

    public void  setHourlyRate(int hourlyRate){
        if (hourlyRate<=0)
            throw new IllegalArgumentException("hourlyRate must be a positive number.");
        this.hourlyRate = hourlyRate;
    }
    public int getHourlyRate(){
        return hourlyRate;
    }

}

```
```
package com.hassandn;

public class Main {
    public static void main(String[] args) {
        var employee = new Employee();
        employee.setBaseSalary(60_000);
        employee.setHourlyRate(58);
        int wage = employee.calculateSalary(35);
        System.out.println(wage);

    }

}


```
## Abstracion
Reduce complexity by hiding unneccessary details
## coupling 
یعنی چقدر یک کلاس به کلاس دیگه وابسته هست هر جقدر وابتسگیه بیشتر باشه کاپلینگ بیشتره مثلا تو مثال بالا داریم میتونیم getter ها رو پرایوت کنیم و دسترسی بهشون رو قط کنیم چون کارشون نداریم و کاپلینگ رو کمتر میکنن 
برای اینکه کاپلینگ بیشتر نشه و از ابسترکشن استقاده کنیم فقط از چیزایی استفاده میکنیم که نیاز داریم 
یک مثالش مثل کنترل تلوزیون هست ما برامون مهم نیست چجوری وقتی دکمه والیوم رو زدیم عوض میشه ما فقط میخوایم عوض بشه برای همین این قسمت ها رو عوض میکنیم برای مثال دیگه این مدل رو برات میارم 
ما یک کلاس داریم که مثل مرورگر قراره سرچ کنه برای فراخونیش ما فقط جواب رو میخوایم دیگه کاری به متد هایی که باید کار کنن تا جواب بیاد نداریم
```
package com.hassandn;

public class Browser {
    public void navigation(String address){
        String ip = findIpAddress(address);
        String htmlResult = sendHttpRequeset(ip);
        System.out.println(htmlResult);
    }

    private String sendHttpRequeset(String ip) {
        return "<html></html>";

    }

    private String findIpAddress(String address) {
        return "127.0.0.1";
    }
}
```
```
package com.hassandn;

public class Main {
    public static void main(String[] args) {
        var browser = new Browser();
        browser.navigation("www.iran.org");
    }

}

```
اینجا وقتی توی مین مینزیم برازر دات دیگه کاری به متد های ریز نداریم 
## constructors
وقتی یک شئ داده جدید میسازیم زبان میاد و اون شئ رو میسازه یک راه برای اینکه کاربر رو مجبور کنیم اونطور که میخوام حتما دیتا رو وارد کنه استفاده از کانستراکتور ها هست برای بهتر شده کد زیر داریم 

```
package com.hassandn;

public class Employee {
    private int baseSalary ;
    private int hourlyRate ;
//    public int extraHour   ;

    public Employee(int baseSalary,int hourlyRate){
        setBaseSalary(baseSalary);
        setHourlyRate(baseSalary);
    }
```
## method overloading
یعنی دو تا تابع با یک اسم باشن و با پیاده سازی های مختلف یعنی برای هر سناریو ما ورودوی بتونیم بگیریم

```
    public int calculateSalary(int extraHour){
        int result = baseSalary + (hourlyRate * extraHour);
        return  result;
    }

    public int calculateSalary(){
        int result = baseSalary;
        return  result;
    }
```
## Cunstructor Overloading
اینجا ما داریم که متدی رو صدا میزنیم که مثلا hourly rate نداشته باشه پس میتونیم خودشو اینطوری صدا کنیم و hourly rate رو صفر بزاریم
```
    public Employee(int baseSalary){
        this(baseSalary,0);
    }

    public Employee(int baseSalary,int hourlyRate){
        setBaseSalary(baseSalary);
        setHourlyRate(baseSalary);
    }
```
## Static members
توی oop کلاس ها میتونن دو تایپ ممبر داشته باشه 
statics and instances
اینتستن ها برای آبجکت ها هستن 
ولی استاتیک ها برای خوده کلاس ها هستن 
ما وقتی از استاتیک ها استفاده میکنیم که متد ما مطلع به شئ داده ای نباشه و میخواید بین تمام شئ ها در اشتراک بزاری  مثلا 
```
Employee.getNumberOfEmployees
```
نکته ای که هست اینکه ما فقط میتونیم به فیلد های استاتیک دسترسی داشته باشیم و به بقیه چیز ها نمیتونیم دسترسی داشته باشیم چون اونها اینتستنس هستن و برای دسترسی بهشون ما نیاز داریم یک آبجکت بسازیم 
ما میتونیم برای ریفکتور کردن از شورت کات های خوده انتلیج استفاده کنیم که خیلی بی خطر کد ها رو جا به جا میکنه و صدا زدنشون رو اوکی میکنه 
پروژه ری فکتور کردن برنامه 
```
package com.hassandn;

public class Main {
    public static void main(String[] args){
        double principal = Console.getInformation("Please enter your principal",1_000, 1_000_000);
        double annualInterest = Console.getInformation("Please enter your annualinterest",0,30);
        int period = (int) Console.getInformation("Please enter the period(years)",0,30);

        var mortgage = new MortgageCalculator(period,annualInterest,principal);
        double result = mortgage.calculateMortgage();
        System.out.println(result);
        MortgageReporter.outputFormat(mortgage.getRemainingBalances());

    }
}
```
```
package com.hassandn;

import java.util.Locale;
import java.util.Scanner;

public class Console {
    public static double getInformation(String prompt, int min, int max){
        Scanner scanner = new Scanner(System.in);
        scanner.useLocale(Locale.US);
        while (true) {
            System.out.print(prompt + ":=> ");
            double userInput = scanner.nextDouble();
            if (min < userInput && userInput <= max){
                return userInput;
            }
            else {
                throw new IllegalAccessError("your response have to be between " + min + " and " + max + "!");

            }

        }
    }
}
```
```
package com.hassandn;

public class MortgageCalculator {
    private final byte MONTHOFYEAR = 12;
    private final byte PERCENT = 100;
    private int period;
    private double annualInterest;
    private double principal;

    private int numberOfPayments;
    private double monthlyInterestRate;

    public MortgageCalculator(int period, double annualInterest, double principal){
        this.principal = principal;
        this.annualInterest = annualInterest;
        this.period = period;

        calculateMothOfPayments();
        calculateMonthlyInterest();
    }

    private void calculateMothOfPayments(){
        numberOfPayments = MONTHOFYEAR * period;
    }

    private void calculateMonthlyInterest(){
        monthlyInterestRate = annualInterest / PERCENT / MONTHOFYEAR;
    }

    public double calculateMortgage(){

        double mortgage = principal * (monthlyInterestRate * Math.pow(1 + monthlyInterestRate, numberOfPayments))
                / (Math.pow(1 + monthlyInterestRate, numberOfPayments) - 1);
        return  mortgage;
    }

    public double calculateBalance(double numberOfPaymentsMade) {

        double balance = principal
                * ( Math.pow(1 + monthlyInterestRate, numberOfPayments)
                - Math.pow(1 + monthlyInterestRate, numberOfPaymentsMade))
                / (Math.pow(1+ monthlyInterestRate, numberOfPayments) - 1);

        return balance;
    }

    public double[] getRemainingBalances(){
        double[] romainBalance = new double[numberOfPayments];
        for (int months = 1; months - 1 < romainBalance.length; months++) {
            romainBalance[months - 1] = calculateBalance(months);
        }
        return romainBalance;
    }

}
```
```
package com.hassandn;

import java.text.NumberFormat;
import java.util.Locale;

public class MortgageReporter {
    static double mortgage;
    public MortgageReporter(double mortgage){
        this.mortgage = mortgage;
    }

    public static void outputFormat(double[] remainBalance){
        System.out.println(mortgage);
        System.out.println("--------");

        for (int i = 0; i < remainBalance.length; i++) {
            convertToCurrency(remainBalance[i]);
        }

    }
    private static void convertToCurrency(double currency){
        String result;
        result = NumberFormat.getCurrencyInstance(Locale.US).format(currency);
        System.out.println(result);

    }
}
```
# inheritance
به کلاس پدر بیس یا سوپر نیر گفته میشه به کلاس چاید هم ساب گفته میشه 
برای اینکه یک کلاس از کلاس دیگه ارث ببره از این روش استفاده میکنیم 
```
package com.hassandn;

public class UIControl {
    private boolean isEnabled = true;

    public void getEnabled(){
        isEnabled = true;
    }
    public void getInabled(){
        isEnabled = false;
    }
    public boolean isEnabled(){
        return isEnabled;
    }
}
```
```
package com.hassandn;

public class TextBox extends UIControl {
    public String text = "";

    public void setText(String text){
        this.text = text;

    }
    public void clear(){
        text = "";
    }
}
```
```
package com.hassandn;

public class Main {
    public static void main(String[] args) {
        var textbox = new TextBox();
        textbox.
    }

}
```
اینجا وقتی تکست باکس رو میزنی متد های کلاس یو ای کنترلر هم میاد 
توی جاوا به صورت اتوماتیک کلاس ها از کلاس آبجکت ارث میبرن این کار هم خوده کامپایلر انجام میده 
فیلد هایی که کلاس آبجکت داره به این صورت هستن 
```
hashCode
toString
equals
```
### constructors
توی کلاس پرنت ما میتونیم کانستراکتور درست کنیم 
```
public class UIControl {
    public UIControl() {
        System.out.println("hello this is UIController");
    }
}
public class Main {
    public static void main(String[] args) {
        var textbox = new TextBox();
//        textbox.
    }

}

```
اینجا وقتی از تکست باکس شئ درست میکنیم پیام میاده 
حالا اگه ما کانستراکترمون پارامتری بگیره که ما نیاز داریم در پرنت باید از استیتمنت super استفاده کنیم
```
private boolean isEnabled = true;
        public UIControl(boolean status) {
            this.isEnabled = status;
            System.out.println("hello this is UIController");

        }

public TextBox() {
        super(true);
        System.out.println("this is text box ");

    }
```
ما یک اکسس مدیفایر دیگه داریم به اسم پروتکتد که به تمام موجودیت های داخل پکیج هستن 
اگه برای فیلدی اکسس مادیفایر نزاری به صورت پیشفرض میشه پروتکتد 
## overriding
یک مثال از اور راید هست وقتی ما از toString() استفاده میکنیم اون میاد و ادرس رو به صورت string میتونیسه و اگه خواسته باشیم چیزه خاصه دیگه ای اضافه کنیم خواهیم داشت که :
برای اینکه اور رایدشون کنیم باید بالاش از انونیشن ها استفاده کنیم @Override
```
package com.hassandn;

public class Main {
    public static void main(String[] args) {
        var textbox = new TextBox();
        textbox.setText("bugatti");
        System.out.println(textbox.toString());
    }

}

  @Override
    public String toSting(){
        return text;
    }
```
انونیشن ها برای این هستن که به کامپایلر جاوا بگیم ما اطلاعات اضافه تری داریم 
## upcasting and downcasting 
رابطه is a داریم ما توی کستینگ 
upcasting : Casting an Object  to one of its super types
downcasting : Casting an Object to one of its sub types
آپ کستینگ یعنی از کلاس بالایی چیزی رو که داره صدا بزنه مثلا این 
```
package com.hassandn;

public class Main {
    public static void main(String[] args) {
        var textBox = new TextBox();
        show(textBox);
    }
    public static void show(UIControl uiControl){
        uiControl.
        System.out.println(uiControl);
    }

}

```
اینجا ما تکست باکس رو دادیم و متد ما پارامتر ورودیش یو ای کنترلر هست اما ما بهش تکست باکس رو دادیم وقتی بخوایم از uiControl ببنیم چه متد هایی داره میبینم که فقط متد های یو ای کنترلر میاد 
اگه بخوایم که از متد های اون کلاس که اوردیم استفاده کنیم از این استفاده میکنیم برای
```
package com.hassandn;

public class Main {
    public static void main(String[] args) {
        var textBox = new TextBox();
        show(textBox);
    }
    public static void show(UIControl uiControl){
        var control = (TextBox) uiControl;
        control.setText();
        System.out.println(uiControl);
    }

}
```
توی این کد داریم داون کستینگ انجام میدیم حالا اینجا یک مشکل پیش میاد ما اگه این رو پیاده سازی کرده باشیم ولی ما بهش آبجکت کلاس یو ای کنتلر رو بدیم اینطوری به خطا بر میخوریم که یو ای text box رو نداره برای حل این مشکل ما میتونیم از instanceof استفاده کنیم 
```
package com.hassandn;

public class Main {
    public static void main(String[] args) {
        var textBox = new TextBox();
        var uictrl = new UIControl(true);
        show(textBox);
        show(uictrl);
    }
    public static void show(UIControl uiControl){
        var control = (TextBox) uiControl;
        control.setText("SSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSssUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUIIIIIIIIIIIITSTTSTI");
        System.out.println(uiControl);
    }

}
```
```
Exception in thread "main" java.lang.ClassCastException: class com.hassandn.UIControl cannot be cast to class com.hassandn.TextBox (com.hassandn.UIControl and com.hassandn.TextBox are in unnamed module of loader 'app')
	at com.hassandn.Main.show(Main.java:11)
	at com.hassandn.Main.main(Main.java:8)
```
راه حل به صورت زیر هست 
```
package com.hassandn;
public class Main {
    public static void main(String[] args) {
        var textBox = new TextBox();
        var uictrl = new UIControl(true);
        show(textBox);
        show(uictrl);
    }
    public static void show(UIControl uiControl){
        if (uiControl instanceof TextBox) {
            var control = (TextBox) uiControl;
            control.setText("SSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSssUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUIIIIIIIIIIIITSTTSTI");
        }
        System.out.println(uiControl);
    }
}
```
ما اگه توی کد بزنیم == بین دو تا شئ که داده هاشون یکی هستن فالس میده این حتی برای equals هم همینطوره 
برای اینکه دوتا آبجکت رو بتونی با هم میتونی از شورت کات هایی که خوده ای دی ای داره استفاه کنی و متد های equals و hash code رو اورراید کنی
```
package com.hassandn;

import java.util.Objects;

public class Point {
    private int x;
    private int y;

    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;
        Point point = (Point) o;
        return x == point.x && y == point.y;
    }

    @Override
    public int hashCode() {
        return Objects.hash(x, y);
    }

    //    @Override
//    public boolean equals(Object obj) {
//        return super.equals(obj);
//    }
}
```
ی راه دیگشم که خودت بتونی اون رو پیاده سازی کنی به این صورت هست  
```
@Override
    public boolean equals(Object obj){
        var other = (Point) obj;
        return  other.x == x && other.y ==y;
    }
```
اینجا چون میتونه هر شئ ای بره داخل این متد ما میتونیم برای جلوگیری از اینکه هر آبجکتی داخلش بره به جز آبجکت های مجاز یک شرط میزاریم
```
    @Override
    public boolean equals(Object obj){
        if (!(obj instanceof Point))
            return false;
        var other = (Point) obj;
        return  other.x == x && other.y ==y;
    }
```
وقتی ما equals رو اورراید کردیم باید hash code رو هم باید اورراید کنیم 
```
@Override
    public int hashCode() {
        return Objects.hash(x,y);
    }
```
# polymorphism
ما دو نوع پولی مورفیسم داریم یکی 
compile time 
runtime
کامپیال تایم همون اوررایدینگ هستش 
ران تایم همون پلی مورفیسم خودمون هست 
فک کن دو تا کلاس داریم که میخوایم از کلاس یو ای کنتلر ارث بری کنن هردوشون 
ولی یک مشکل وجود داره توی تابع مین نمیتونیم بنویسیم که اگه آبجکت ما فلان چیز بود پس ui render اون کلاس رو اجرا کن اینجوری هی مجبوریم با هر کلاسی که اضافه میکنیم برای ارث بری اون رو بهش اضافه کنیم 
بهترین کار اینکه برای 
```
package com.hassandn;

public class UIControl {
    private boolean isEnabled = true;
        public UIControl(boolean status) {
            this.isEnabled = status;
            System.out.println("hello this is UIController");

        }
        public void render() {

        }


    public void getEnabled(){
        isEnabled = true;
    }
    public void getInabled(){
        isEnabled = false;
    }
    public boolean isEnabled(){
        return isEnabled;
    }

//    public abstract String toSting();
}
package com.hassandn;

public class TextBox extends UIControl {
    public String text = "";

    @Override
    public String toString(){
        return this.text;
    }

    @Override
    public void render() {
        System.out.println("text box implementation ui");
    }

    public TextBox() {
        super(false);
        System.out.println("this is text box ");

    }

    public void setText(String text){
        this.text = text;

    }
    public void clear(){
        text = "";
    }
}
package com.hassandn;

public class CheckBox extends UIControl{

    public CheckBox(){
        super(true);
    }

    @Override
    public void render() {
        System.out.println("this is check box implementation ui");
    }
}
package com.hassandn;

public class Main {
    public static void main(String[] args) {
        UIControl[] controls = {new TextBox(), new CheckBox()};
        for (var control : controls){
            control.render();
        }
    }

}	
```
## abstrac
ابسترک ماله وقتی هست که یک چیز معمول رو میخوایم بدیم که بقیه بنویسن و پیاده سازی کنن مثلا ما رندر کلاس uicontrol رو نداریم و اصلا مفهومی نداره ولی برای تکست باکس و چک باکس داریم این موضوع رو 
ما برای اینکه یک متد رو بگیم ابسترک هست از کلمه abstract استفاه میکنیم 
```
package com.hassandn;

public abstract class UIControl {
    private boolean isEnabled = true;
        public UIControl(boolean status) {
            this.isEnabled = status;
            System.out.println("hello this is UIController");

        }
        public abstract void render() ;


    public void getEnabled(){
        isEnabled = true;
    }
    public void getInabled(){
        isEnabled = false;
    }
    public boolean isEnabled(){
        return isEnabled;
    }

//    public abstract String toSting();
}
```
حالا بقیه کلاس هایی که از این ارث میبرن باید رندر رو پیاده سازی کنن
و اگه یکی رو نخواستیم پیاده سازی کنیم خواهیم داشت 
```
@Override
    public abstract void render();
```
## final classes and methods
برای وقتی هست که میخوایم کلاس رو کسی نتونه اورراید کنه و کاره مهمی داریم برای مثال داریم یک استیت رو در دیتا بیس عوض میکنیم 
این برای متد ها هم به همین صورت هست 
لول ارث بریت نهایت تا سه مرحله باشه
## multiple inheritance

## oop concepts => 1. Encapsulation 2. Abstraction 3. polymorphism
# YANGI (you aren't gonna need it)
# interfaces
we use interfaces to build loosely-coupled, extensible, tastable applications.
interfaces : what should be done
classes : how it should be done
فرض کن که ما دو تا کلاس داریم کلاس a و کلاس b کلاس ای از کلاس بی ارث بری میکنه اگه ما کد کلاس بی رو تغییر بدیم به مشکل باید کلاس ای هم تغییر بدیم ولی خب اینجا زیاد ما اذیت نمیشیم ولی اگه برنامه ما از صدها یا هزاران ماژول ساخته شده باشه اینجاست که ما به مشکل برخورد خواهیم کرد برای همین از یک واسطه استفاده میکنیم به اسم اینترفیس ها 


```
package com.hassandn;

public class TaxCalculator {
    private double taxabeleIncome;

    public TaxCalculator(double taxabeleIncome) {
        this.taxabeleIncome = taxabeleIncome;
    }

    public double calculateTax(){
        return taxabeleIncome * 0.3;
    }
}
package com.hassandn;

public class TaxReporter {
    TaxCalculator taxCalculator = new TaxCalculator(100_000);

    public void show(){
        System.out.println(taxCalculator.calculateTax());
    }

}
package com.hassandn;

public class Main {
    public static void main(String[] args) {
        var taxreporter = new TaxReporter();
        taxreporter.show();
    }

}
```
ما اینجا مشکل داریم که ریپورتر ما خیلی وابسته هست به کلکیولیترمون 
برای نام گذاری اینترفیس هامون توی c# اوله اسمه ماژول ای بزرگ میزارن ولی توی جاوا میتونیم از چیزای مثل 
Can...
.....Able
این اسم گذاری ها رو استفاه میکنن تا بگن این اینترفیس هست 
```
package com.hassandn;

public interface CanCalculateTax {
    public double calculateTax();
}
```
ما توی اینترفیس فقط این رو خواهیم داشت 
البته استفاده از پابلیک ی جورایی اضافه هست چون برای استفاده از متد ها اونها باید حتما پابلیک باشن تا بتونیم به اونها دسترسی داشته باشیم
خب ما برای استفاده کردن از اینترفیس ها نمیتونیم شئ درست کنیم چون پیاده سازی ای ازش نشده برای همین راه دیگه ای داریم برای انجام کارمون باید بریم کلاسی که کار رو انجام میده و بعدش اضافه کنیم که implements 
## dependency injection
یعنی اینکه استفاده کردن از آبجکت و ساختن آبجکت هردو چیزهای متفاوتی هستن  سه راه وجود داره برای اینکار 
constructor injection
setter injection
method injection

یعنی میایم تو اونی که باید استفاده بکنه ازش میگیم ی متغیری از جنس اینترفیس قراره که بیاد تو بیا اینو بگیر و از متدی که نیاز داریم استفاده کن 
(پس توی انیجکشن ما میدونیم از نوع یک کلاسی قراره شئ ساخته بشه و بهمون داده بشه ولی برامون مهم نیست اسمش چیه)
یک مثالی که خودم نوشتم
### Constructor Injection
```

package com.test;

public class Main {
    public static void main(String[] args){
        TaxCalculator2024 taxcalculator = new TaxCalculator2024(5_000_000);
        TaxReporter taxreporter = new TaxReporter(taxcalculator);
        taxreporter.show();
    }
}

package com.test;

public class TaxReporter {
    private CanCalculateTax taxcalculator;

    public TaxReporter(CanCalculateTax taxcalculator) {
        this.taxcalculator = taxcalculator;
    }

    public void show(){
        System.out.println(taxcalculator.calculateTax());
    }
}
package com.test;

public interface CanCalculateTax {
    double calculateTax();
}
package com.test;

public class TaxCalculator2024 implements CanCalculateTax {
    private double calculatableIncme;

    public TaxCalculator2024(double calculatableIncme) {
        this.calculatableIncme = calculatableIncme;
    }
    @Override
    public double calculateTax(){
        return calculatableIncme * 0.3;
    }
}
```
### Setter Injection
اگه میخوای که توی لایف تایم برنامه دپندنسی ها رو عوض کنی از ستتر اینجکشن استفاده میکنی 
```
package com.hassandn;

public class TaxCalculator2025 implements CanCalculateTax{

    @Override
    public double calculateTax() {
        return 0;
    }
}
package com.hassandn;

public class TaxReporter {
    private CanCalculateTax taxCalculator;
//    TaxCalculator2024 taxCalculator = new TaxCalculator2024(100_000);

    public TaxReporter(CanCalculateTax taxCalculator) {

        this.taxCalculator = taxCalculator;
    }

    public void show(){
        System.out.println(taxCalculator.calculateTax());
    }

    public void setTaxCalculator(CanCalculateTax taxCalculator) {
        this.taxCalculator = taxCalculator;
    }

}
package com.hassandn;

public class Main {
    public static void main(String[] args) {
        var result = new TaxCalculator2024(100_000);
        var taxresult = new TaxReporter(result);
        taxresult.show();
        taxresult.setTaxCalculator(new TaxCalculator2025());
        taxresult.show();
    }

}
```
توی این کد برای ریپورتر یک ستر ساختیم و بعد توی مین هرچی خواستیم رو بهش دادیم 
### method injection
توی این میایم و توی همون متد شو آبجکت رو صدا میزنیم بیشتر مردم از کانستراکتور استفاده میکنن
```
package com.hassandn;

public class TaxReporter {
    public void show(CanCalculateTax taxCalculator){
        System.out.println(taxCalculator.calculateTax());
    }
}
```
برخلاف کلاس ها در جاوا اینترفیس ها میتونن چند تا پرنت داشته باشن 
### Interface Segregation Principle
Divide big interfaces into smaller ones
یعنی اگه مثلا یک اینترفیسی داری که چند تا متد داره و متد ها به هم بی ربط هستن باید اونها رو جدا کنی
چون وقتی مثلا یک کلاس از یک متد استفاده کرده باشه و کاری اصلا به بقیه اینترفیس ها نداشته باشه ولی دوباره باید کد به خاطر اون کامپایل بشه 
برای مثال در کد زیر داریم 

### practice for myself
```
package com.hassandn;

public class Main {
    public static void main(String[] args){
        var taxcalculator = new TaxCalculator2024(120_000);
        var taxreporter = new TaxReporter(taxcalculator);
        taxreporter.show();
    }
}
package com.hassandn;

public class TaxReporter {
    private CanCalculateTax calculateTax;

    public TaxReporter(CanCalculateTax calculateTax) {
        this.calculateTax = calculateTax;
    }

    public void show(){
        System.out.println(calculateTax.calculateTax());
    }
}
package com.hassandn;

public interface CanCalculateTax {
    double calculateTax();
}
package com.hassandn;

public class TaxCalculator2024 implements CanCalculateTax {
    private double income;
    public TaxCalculator2024(double income) {
        this.income = income;
    }

    @Override
    public double calculateTax(){
       return income * 0.3;
    }
}

```
این روش برای constructor injection هست 
یکی از خوبی های استفاده از اینتفرفیس استفاده از یونیت تست ها هستن 
ما در چند سال اخیر مفاهیم جدیدی از اینترفیس ها داریم در جاوا که بهشون میگیم اینترفیس ها 
# java features
## java interfaces features
### Fields
تو میتونی توی اینترفیس ها از کانستراکتور ها استفاه کنی و یک مقداری رو به صورت فاینال بدی به اینترفیس این کار جالب نیست چون اون فیلد مخصوص به پیاده سازی هست و ربطی به اینترفیس نداره و میتونه توی خوده پیاده سازی باشه برای مثال توی همین مثالی که داریم 
```
package com.mytube;

public interface CanNotification {
    int Price = 1_000;
    void sendNotification(User user);

}
package com.mytube;

public class EmailService implements CanNotification {
    private Video video;
    private User user;
    public EmailService(Video video) {
        this.video = video;
//        this.user = user;
    }


    @Override
    public void sendNotification(User user) {

        System.out.println("Notifying " + user.getEmail() + "..." + CanNotification.Price);
        System.out.println("Done!\n");
    }
}
Notifying john@domain.com...1000
Done!
```
### Static methods
ما میتونیم متد های استاتیک درست کنیم توی اینترفیس ها ولی اینجا یک مشکلی پیش میاد که اینترفیس الان پیاده سازی داره 
interfaces are about whats not how's
how's are for classes
خب حالا سوال پیش ماید که ما ی چیز میخوایم که پیاده سازیش توی همه متد ها باید باشه اونجا ما از کلاس های ابسترک استفاده میکنیم 
```
package com.hassandn;

public interface CanCalculateTax {
    double calculateTax();

    static double getTaxableIncome(double income, double expences){
        return income - expences ;
    }
}

```
کدی که خواهیم داشت 
```
package com.hassandn;

public interface CanCalculateTax {

//    CanCalculateTax();

    void calculateTax();


}
package com.hassandn;

public class TaxCalculator2025 extends AbstractTaxCalculator {
    public void calculateTax() {
        getTaxableIncome(1_000_000,50_000);
    }
}
package com.hassandn;

public class AbstractTaxCalculator implements CanCalculateTax{

    protected static double getTaxableIncome(double income, double expences){
        return income - expences ;
    }


    @Override
    public void calculateTax() {
        return 0;
    }
}
```
### private methods
ما میتونیم توی اینترفیس ها متد های پرایوت درست کنیم که دلیلش این هست که وقتی از استاتیک ها استفاده میکنی ی سری متد ها رو درست کنی تا کد کمتری توی استاتیک ها استفاده بشه 
### interview questions

فرق abstract و interface توی چی هست 
#### interface : To Build loosely-coupled, extensible, testable applications
#### Abstraction : To share code
اگه ازت خواستن فرق  اینترفیس و ابسترکشن بکی داستان های پشتشون رو بگو و داستان
hint: میتونیم برای اینکه ماکسین داشته باشیم در کلاس ها از اینترفیس ها استفاده کنیم چون میتونیم هر چند تا رو خواستیم implement کنیم 
سودمندی های استفاده کردن از اینترفیس ها 
1.متیونیم پیاده سازی ها رو تغییر بدیم 
2. میتونی برنامت رو گشترش بدی با تاثیرات کم 
3. میتونی کلاستو تست کنی توی ایزولیشن 
هواست باشه که هر چیزی که درست میکنی دلیل خودش رو داشته باشه ساختن بی خودی اینها هم باعث اضافه تر شدن پولش میشه
Dependency injection refers to passing or injecting dependencies of a
class. 
# advanced java
## Exception
وقتی به اروری برمیخوریم میگن که متد اکسپشن رو throw کرد 
مثالی از یک اکسپشن
```java
package com.exeptions;

public class Main {
    public static void main(String[] args){
        ExceptionDemo.show();
    }
}
package com.exeptions;

import java.util.Locale;

public class ExceptionDemo {
    public static void show(){
        sayHello(null);
    }
    public static void sayHello(String name){
        System.out.println(name.toUpperCase(Locale.ROOT));
    }
}
```
```
Exception in thread "main" java.lang.NullPointerException: Cannot invoke "String.toUpperCase(java.util.Locale)" because "name" is null
	at com.exeptions.ExceptionDemo.sayHello(ExceptionDemo.java:10)
	at com.exeptions.ExceptionDemo.show(ExceptionDemo.java:7)
	at com.exeptions.Main.main(Main.java:5)
```
اینجا میاد و از جایی که مشکل هست شرواع میکنه میگرده اگه اکسپشن هندلر نداشته باشیم میاد و از جایی که صدا زده شده اون متد و اون رو فراخونی میکنه اگه اونجا هم اکسپشن هندلر ننوشته باشیم براش همینطور برمیگرده عقب
توی کدمون یا باید برای هر ارور یک اکسپشن داشته باشیم یا بتونیم که خوب هندلشون کنیم 
#### types of Exceptions
1. checked
2. unchecked
3. error
   اولی مربوط به این هست که مربوط به کامپایل هست و در زمان کامپایل اون رو چک میکنه برای مثال میگیم که یک فایل رو باز کنه توی مرحله کامپایل میاد اون رو چک میکنه و ارور میده
   دومی رانتایم هست که وقتی در حال اجرا هست یک مشکلی بهش برمیخوریم و ارور میگیریم
   ارور هم مثلا استک اور فلو ایندکس اوت اف رنج یا مموری اوت اف رنج و... هست
   همه اکسپشن های ما از کلاس throwable میان زیر اون کلاس Error هست که مربوط به ارور هایی که هست که مربوط به برنامه ما نیست و کلاس Exception که مربوط به ارور های ما مربوط به زمان کامپایل هست
   زیره Exception ما RuntimeException داریم 
متدوال ترین اکسپشن های ران تایم به صورت زیر هستن
1. NullPointerException
2. ArithmeticException
3. IllegalArgumentException
4. IndexOutOfBoundsException
5. IllegalStateException

   خب حالا فرض کن میخوایم کدی بنویسیم که کاربر فایلش اگه باز نشد اکسپشن بگیره پس داریم
```
package com.exeptions;

import java.io.FileReader;

public class Main {
    var file = new FileReader("text.txt");
    
}
```
ما این کد رو که بنویسیم زیر میزنه که داداش اصلا وجود نداره و باید براش تست بنویسی
میتونی از خوده ای دی ای استفاده کنی یا میتونی خودت دستی اضافه کنی روش خودکار به صورت زیر هست :
```
public class Main {

    {
        try {
            var file = new FileReader("text.txt");
        } catch (FileNotFoundException e) {
            throw new RuntimeException(e);
        }
    }

}
```
اروری که ما اینجا میگیریم به این صورت هست :
```
Exception in thread "main" java.lang.RuntimeException: java.io.FileNotFoundException: text.txt (The system cannot find the file specified)
	at com.exeptions.Main.main(Main.java:12)
Caused by: java.io.FileNotFoundException: text.txt (The system cannot find the file specified)
	at java.base/java.io.FileInputStream.open0(Native Method)
	at java.base/java.io.FileInputStream.open(FileInputStream.java:213)
	at java.base/java.io.FileInputStream.<init>(FileInputStream.java:152)
	at java.base/java.io.FileInputStream.<init>(FileInputStream.java:106)
	at java.base/java.io.FileReader.<init>(FileReader.java:60)
	at com.exeptions.Main.main(Main.java:10)

Process finished with exit code 1
```
این ارور استاندارده خوده جاوا هست 
برای دستیش میتونیم این رو بنویسیم 
```
try {
            var file = new FileReader("text.txt");
        }catch (FileNotFoundException ex){
            System.out.println("file doesn't exist.");
        }
```
```
try {
            var file = new FileReader("text.txt");
        }catch (FileNotFoundException ex){
            System.out.println(ex.getMessage());
        }
```
ما اگه این خط رو بهش اضافه کنیم باز به این ارور میخوریم که باید براش اکسپشن تعریف کنیم 
```
try {
            var file = new FileReader("text.txt");
            var reader = file.read();
            
        }catch (FileNotFoundException ex){
            System.out.println(ex.getMessage());
        }
        catch (IOException e) {
            throw new RuntimeException(e);
        }
```
کد به این صورت نوشته میشه حالا اگه ترتیب این اکسپشن ها رو عوض کنیم میبینیم که مینه که 
```
try {
            var file = new FileReader("text.txt");
            var reader = file.read();
        }
        catch (IOException exa) {
            throw new RuntimeException(exa);
        }
        
        catch (FileNotFoundException ex){
            System.out.println(ex.getMessage());
        }
    }
```
```
Exception 'java.io.FileNotFoundException' has already been caught
```
این میگه همین الان ما این اکسپشن رو گرفتیم 
پس ترتیب گذاشتن ارور ها مهم هست توی جاوا چون طبق داکیومنت خوده جاوا داریم :
```
java.io.IOException
	java.io.FileNotFoundException
```
این نمونه ای از پولی مورفیزم هست 
و این به این معنی هست که میتونیم کچ آخری رو برداریم 
برای اینکه دوتا اکسپشن رو بگیم یک پاسخ رو بگن داریم :
```
    try {
            var file = new FileReader("text.txt");
            var reader = file.read();
            new SimpleDateFormat().parse("");
        }
        catch (IOException | ParseException exa) {
            throw new RuntimeException(exa);
        } catch (ParseException e) {
            throw new RuntimeException(e);
        }
```
### finally block
اینجا ی سری مشکل هست مثلا وقتی که فایل ریدر رو ازش ابجکت میسازیم os میاد و یک قسمت رو به ما میده و این باعث میشه که بقیه نرم افزار ها نتونن به اون بخش دسترسی داشته باشن برای همین باید اون رو ببندیم برای همین از finally استفاده میکنیم 

```java
FileReader file = null;
        try {
            file = new FileReader("text.txt");
            var reader = file.read();
            new SimpleDateFormat().parse("");
        } catch (IOException | ParseException exa) {
            throw new RuntimeException(exa);
        } finally {
            if (file != null) {
                try {
                    file.close();
                }catch (IOException e){
                    e.printStackTrace();
                }
            }
        }
    }
```
کد به این صورت خواهد شد این کد ی خورده مشکل داره برای همین توی در زیر نسخه بهتر شدش رو داریم 

### try with resources
وقتی از این استفاده کنیم خودش میاد و به صورت explicitly (ضمنی) اون ها رو کلوز میکنه 
The try-with-resources statement is a try statement that declares one or more resources. A resource is an object that must be closed after the program is finished with it.
```
try (
                var file = new FileReader("text.txt")
        ) {
            var reader = file.read();
            new SimpleDateFormat().parse("");
        } catch (IOException | ParseException exa) {
            throw new RuntimeException(exa);
        } 
```
توی این کد دیگه خوده جاوا میاد و این ها رو وقتی کار تموم شد تمومشون میکنن
### throwing exceptions

```java
public void deposit(float value){
        if(value <= 0){
            throw new IllegalArgumentException("meow");
        }
    }
```
این unchecked یا runtime exception هست 
به این کار میگن  defensive programing
#### defensive programing
یعنی وقتی به مشکلی خوردیم ما یک اکسپشن پرتاب میکنیم و از ادامه برنامه جلوگیری میکنیم 
اینو معمولا وقتی استفاده کن که ورودی از کاربر گرفتی یا میخوای که از سیستم یک چیزو چک کنی
```
public void deposit(float value) throws IOException{
            if(value <= 0){
                throw new IOException();
            }
        }
var acc = new Account();
        try {
            acc.deposit(3444);
        } catch (IOException e) {
            throw new RuntimeException(e);
        }
```
اینجا میگیم که این متد شاید یک Ioexception بده توی تابع مین هم یک ترای مزنیم 
Rethrowing Exceptions

#### custom Exception
برای اینکه اکسپشن های کاستوم درست کنیم باید ببینیم که چه نوع اکسپشنی میخوایم بدیم 
1. checked Exception -> Exceotion class
2. unchecked Exception -> RuntimeException
برای مثال فک کن میخوایم یک اکسپشن درست کنیم که کاربر اگه از مقدار پولش بیشتر درخواست برداشت داد اکسپشن بخوره اون وقت خواهیم داشت:
```
package com.exeptions;

public class InsufficientFundsException extends Exception{

    public InsufficientFundsException(){
        System.out.println("you dont have enough money!");
    }

    public InsufficientFundsException(String message){
        super(message);
    }

}
public void withDraw(float value) throws InsufficientFundsException{
            if (value > balance)
                throw new InsufficientFundsException();
        }
}
package com.exeptions;

import java.io.IOException;

public class Main {
    public static void main(String[] args) {
        var acc = new Account();
        try {
            acc.withDraw(15);
        } catch (InsufficientFundsException e) {
            throw new RuntimeException(e.getMessage());
        }


    }
}

```
تو خوده تابع میگیم که ارور میده و وقتی که خواستیم صداش بزنیم از ترای کچ استفاده میکنیم 
chaining exceptions
میتونیم طوری بزاریم اکسپشن ها رو که بگیم این خطا به خاطر فلان خطا رخ داد
