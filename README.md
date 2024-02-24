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
```java
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
```java
package com.exeptions;

import java.io.IOException;

public class Main {
    public static void main(String[] args) {
        var acc = new Account();
        try {
            acc.withDraw(-1500);
        }catch (AccountException e){
            e.getStackTrace();
        }

    }
}
package com.exeptions;

public class AccountException extends Exception {
    public AccountException(Exception cause){
        super(cause);
    }
}
package com.exeptions;

import java.io.IOException;

public class Account {
        private float balance;
        public void deposit(float value) throws IOException{
            if(value <= 0){
                throw new IOException();
            }
        }

        public void withDraw(float value) throws AccountException{
            if (value < balance)
                throw new AccountException(new InsufficientFundsException());
        }
}

```
با این کدا تریس بک نشون میده که فلان ارور رو برخورد کردیم به خاطر فلان چیز
## generics	
```java
package com.exceptions;

public class IntList {
    int[] list = new int[10];
    private int index;

    public void add(int value){
        list[index++] = value;
    }

    public void get(int index){
        System.out.println(list[index]);
    }

}
package com.exceptions;

public class Main {
    public static void main(String[] args){
        var intlst = new IntList();
        intlst.add(5);
        intlst.add(3);
        intlst.get(1);
        intlst.get(0);
    }
}
```
اول طرح مشکل میکنیم 
فزض کن که یک فایلی درست کردی که توی این لیست ما int نگه میداریم و پیاده سازی برای اضافه کردن و پاک کردن هم بهش اضافه میکنیم 
حالا فک کن یک لیست برای یوزر ها میخوایم با همون پیاده سازی ها دوباه ی لیست برای استرینگ ها و همینطور پیش میره به جلو اینجا برای حل این مشکل ما راهکاری داریم 
اون وقت میتونیم به جای اینکه بنویسیم int یا user مینویسیم object اینطوری ما لیستی از آبجکت ها خواهیم داشت 
```java
package com.exceptions;
public class IntList1 {
    Object[] mylist = new Object[10];
    private int index;

    public void add(Object value){
        mylist[index++] = value;
    }

    public void get(int index){
        System.out.println(mylist[index]);
    }

}
package com.exceptions;

public class Main {
    public static void main(String[] args){
//        var intlst = new IntList();
//        intlst.add(5);
//        intlst.add(3);
//        intlst.get(1);
//        intlst.get(0);
//        System.out.println("start");
        var objlist = new IntList1();
        objlist.add(2);
        objlist.add("Hello there");
        objlist.add(true);
        objlist.get(0);
        objlist.get(1);
        objlist.get(2);

    }
}
```
```
start
2
Hello there
true
```
اگه هم که با آبحکت اون رو درست کنیم به صورت بالا هست 
مثلا یک مشکلی که ما بهش میخوریم اینکه میگیم گت کن آیتم اولی رو توی یک متغیر که اینت هست ولی مشکل این هست دقیقا که ما نمیدونیم اون چیه و باید آبجکت باشه برای اینکار باید اون رو کست کنیم که باز به مشکل میخوریم اگه تایپی که انتخاب کرده بودیم اشتباه بود 
```java
	int num = (int)objlist.get(0);//it's kinda ugly code
	int num = (int)objlist.get(1);//it's get casting error
```
 برای گرفتن پارامتر در کلاس ها در جاوا ما از این روش زیر استفاده میکنیم 
```java
package com.exceptions;

public class Generics<T> {
}
```
داخل <> ما عددمون رو میزاریم به همین راحتی 
```java
package com.exceptions;

public class Generics<T> {
    private T[] mylist = (T[])new Object[10];
    private int count;

    public void add(T value){
        mylist[count++] = value;
    }

    public void get(int count){
        System.out.println(mylist[count]);
    }
}
```
اینجا میایم و ی لیست درست میکنیم که جنس تی  توش ذخیره میشه و ما تا زمان اجرای برنامه نمیدونیم T چی میتونه باشه 
معنی خط دوم اینکه ما یک متغیر پرایوت داریم به اسم mylist  ما چون موقع اجرا معلوم میشه جنسه تی چی هست و به خطا میخوریم برای همین به جای object[10] میزاریم که به ارور نخوریم و هرچی شد تایپش زیره Object باشه در نهایت اون رو کس کید میکنیم توی لیستی از تی 
بقیشم که مشخصه رفیث :)
ما رفرنس تایپ داریم و پریمیتیو تایپ رفرنس تایپ ها چون زیره Object هستن میتونیم اونها رو بزاریم برای تایپ و بعد مقابلشون بزاریم که جنسی از Object هست برای همین ما از wrapper class ها استفاده میکنیم که یک اینتسنس درست میکنن
برای مثال داریم 
```
float -> Float
int -> Integer
boolean -> Boolean
```
wrapper به کلاس هایی گقته میشه که داده های اولیه رو میگیرن و تبدیل میکنن به شئ داده 
به تبدیل از پریمیتیو تایپ به رفرنس تایپ باکسینگ و از تبدیل شدن رفنرس به پریمیتیو میگن آنباکسینگ
```java
package com.exceptions;

public class Main {
    public static void main(String[] args){
    var asap = new Generics<Integer>();
    asap.add(3); // boxing
   int number = asap.get(0); // unboxing    

    }
}
```
### constraints
اگه خواستیم محدود کنیم که نوع خاصی از ابجکت داشته میتونیم از کانترینتس استفاده کنیم که اونها رو محدود کنه برای مثال اگه خواستیم حتما عدد داشته باشه خواهیم داشت:
```
package com.exceptions;

public class Generics<T extends Number>{
    private T[] mylist = (T[])new Object[10];
    private int count;

    public void add(T value){
        mylist[count++] = value;
    }

    public void get(int count){
        System.out.println(mylist[count]);
    }
}
```
در کد بالا فقط میشه که عدد باشن float int short long  اگه خارج از اینا باشن نمیشه ما همچینین Comparable داریم که میگه آبجکت هایی که قابل مقایسه هستن باشن برای مثال اگه خواستیم یک آبجکتی درست کنیم که کامپریبل باشه از زیر استفاده میکنیم 
```
package com.exceptions;

public class User implements Comparable {
}
package com.exceptions;

public class Generics<T extends Comparable>{
    private T[] mylist = (T[])new Object[10];
    private int count;

    public void add(T value){
        mylist[count++] = value;
    }

    public void get(int count){
        System.out.println(mylist[count]);
    }
}
```
اون وقت میتونیم از نوع داده یوزر استفاده کنیم 
همچنین میتونیم دو تا محدودیت هم بزاریم 
```
package com.exceptions;

public class Generics<T extends Comparable & Cloneabe>{
    private T[] mylist = (T[])new Object[10];
    private int count;

    public void add(T value){
        mylist[count++] = value;
    }

    public void get(int count){
        System.out.println(mylist[count]);
    }
}
```
#### type erasure 
این میگه که کامپایلر وقت ی جنریک میسازیم فایل بایت کدش تبدیل میشه به کدی که تایپ آبجکت ها برابر هست با Object اگه اون ها رو constrain کنیم توی بایت کد توش میاد و از اون محدودیت استفاده میکنه برای مثال داریم:
```bytecode
public class com/exceptions/Generics {

  // compiled from: Generics.java

  // access flags 0x2
  // signature [TT;
  // declaration: mylist extends T[]
  private [Ljava/lang/Object; mylist

  // access flags 0x2
  private I count

  // access flags 0x1
  public <init>()V
   L0
    LINENUMBER 3 L0
    ALOAD 0
    INVOKESPECIAL java/lang/Object.<init> ()V

```
توی این کد بدون محدودیته اگه محدودیت مثلا نامبر بزاریم به جای آبجکت میزاره نامبر 
حالا بحث type erasure اینجاست که وقتی دو تا محدودیت بزاریم کامپایلر میاد و فقط سمت چپی رو پیاده سازی میکنه یعنی اینکه اگه محدودیت ها به ترتیب از سمت چپ comparable & cloneable باشه کامپیرابل توی کد استفاده میشه 
```
PUTFIELD com/exceptions/Generics.mylist : [Ljava/lang/Comparable;
    RETURN
   L2
```
#### comparable interface
برای اینکه دو شئ رو با هم مقایسه کنیم داریم:
```java
package com.exceptions;

public class User implements Comparable<User> {
    private int points;

    public User(int points){
        this.points = points;
    }

    @Override
    public int compareTo(User other) {
        return points - other.points;
//        return 0;

    }
}
package com.exceptions;

public class Main {
    public static void main(String[] args){

        var user1 = new User(10);
        var user2 = new User(200);
        if  (user2.compareTo(user1)<0)
            System.out.println("It's lower");
        else if (user2.compareTo(user1) == 0)
            System.out.println("it's equal");
        else
            System.out.println("it's bigger");
    }
}

```
اگه مثبت برگردونه یعنی بزرگتر اگه منفی برگردونه یعنی کوچک تر و اگه صفر برگردونه یعنی مساوی بودن
#### generic method
متد های جنریک رو میشه به این صورت نوشت برای مثال داریم 
```java
package com.exceptions;

public class Utils {
    public static <T extends Comparable<T>> T max(T first,T second){
       return (first.compareTo(second) < 0) ? first : second;
    }
}
    @Override
    public String toString(){
        return "Points :=> " + points;
    }
```
با این کد حتی یوزر ها هم متیونیم مقایسه کنیم 
اینجا چون از کامپیربل استفاده کردیم و توی یوزر اون صدا زده میشه و نتیجه رو نشون میده 
#### multiple types parameters
میتونیم هم متد درست کنیم و هم کلاس برای همین 

```java
public static <K ,V> void print(K key, V value){
        System.out.println("Key : " + key + " has value:=> " + value);

    }
```
```java
package com.exceptions;

public class KeyValuePair<K, V> {
    private K key;
    private V value;

    public KeyValuePair(K key,V value){
        this.key = key;
        this.value = value;
    }
}
```
#### 11- Generic Classes and Inheritance
اینجا رو خودم دقیق متوجه نشدم ولی خب...
یک کلاس درست میکنیم به نام Instructor که از کلاس یوزر ارث بری میکنه 
```java
package com.exceptions;

public class Instructor extends User {
    public Instructor(int points){
        super(points);

    }
}

```
بعد از اون توی کلاس یوتلیز یک تابع درست میکنیم به نام پرینت یوزرز که پارامترش از جنس یوزر هست به اسم یوزر
```java
public static void printUser(User user){
        System.out.println(user);
    }
```
بعد از اون میتونیم توی تابع مین به جای یوزر اینستراکتور رو بدیم به متدمون و مشکلی ایجاد نمیشه :
```java
package com.exceptions;


public class Main {
    public static void main(String[] args){
        var user = new Instructor(39);
        Utils.printUser(user);
    }
}
```
حالا فرض کن که یک جنریک لیست از یوزر میخوایم درست کنیم و اون رو بگیریم 
```java
public static void printUser(Generics<User> users)
{
    ;
}
```
```java
	var users = new Generics<User>();
        Utils.printUser(users);
```
اینجا ما به مشکلی برخورد نمیکنیم به تنها مشکلی که برخورد میکنیم اونجا هست که Instroctur رو بهش میدیم اونجاست که ما به مشکل برخورد میکنیم 
```java
        var users = new Generics<Instructor>();
        Utils.printUser(users);
```
الان مشکل این هست که ما زدیم تایپش یوزر باشه توی printUser ولی ما Inatroctur  دادیم که این مشکل ایجاد میکنه چون جنریک لیسته Instoctur زیرگروه جنریک لیسته User نیست برای همین خطا میده و میگه که داداچ گفتی یوزر میدی یک راه برای اینکه این خطا پیش نیاد این هست که بریم و دونه دونه از لیسته Instuctor بگیریم و به User بدیم 
راه دیگه برای این کار استفاده از Wild carts هست 
#### Wild carts
وایلد کارتز یعنی اینکه بگیم تاپیش معولم نیست 
```java
	//	Cap#1 extends User
    public static void printUser(Generics<?> users)
    {
                Object x = users.get(0);
    }
```
وقتی که این ها رو درست میکنیم یا باید از کلاس کپچر باشه که ما دسترسی نداریم بهش یا باید بیس تایپش باشه که Object هست 
انیجا میتونیم دیگه از هر نوع تایپی استفاده کنیم ولی مشکل اینکه حتی میتونیم از تایپ های دیگه ای مثل Int & String استفاده کنیم برای ایجاد این محدودیت از کلاس User ارث بری میکنیم :
```java
	// Cap#1 extends User
    public static void printUser(Generics<? extends User> users)
    {
        ;
    }
```
ما نمیتونیم آبجکت رو توی instructor سیو کنیم چون cap#1 و instuctor هر دوتاشون زیر شاخه user هستن و وقتی میخوایم سیو کنیم از cap استفاده میشه برای همین فقط میتونیم از پرنت های اون استفاده کنیم 

اینجا میتونیم اینجا از لیست بخونیم ولی نمیتونیم اد کنیم اگه بخوایم اد کنیم باید از کلمه super به جای extends  استفاده کنیم 
ولی این رو به یاد داشته باش برای سیو مردن نمیتونی توی User جنسش رو بزاری چون کامپایلر نمیدونه جنسی که قراره بر گرده واقعا یوزر هست یا نه 
```java
	// User x = users.get(0); incorrect
	Object x = users.get(0); // correct
```
اگه خواستیم ازش بخونیم از extends استفاده میکنیم 
اگه خواستیم توش اضافه کنیم از super استفاده میکنیم  
## Collections
The Collection in Java is a framework that provides an architecture to store and manipulate the group of objects.
### iterable
فرض کن میخوای که از جنریکمون همه دیتا ها رو بخونیم اینجا یک راهش این هست که لیست رو که داخل حنریک لیست هست رو پابکیک کنیم که این داره اصل ابسترکشن رو بهم میزنه 
```java
package com.exceptions;

public class Generics<T>{
    public T[] mylist = (T[])new Object[10];
    private int count;

    public void add(T value){
        mylist[count++] = value;
    }

    public T get(int count){
        return mylist[count];
    }
}
package com.exceptions;


public class Main {
    public static void main(String[] args){

        var list = new Generics<String>();
        list.mylist[0] = "a";
        for (String item : list.mylist){
            System.out.println(item);
        }

    }
}
```
مشکلی که اینجا به وحود میاد اینکه اگه خواستی لیست رو عوض کنیم و به جاش ArrayList بزاریم اون وقت مشکل برای ما پیش میاد چون از اون نمیشه ایندکس گرفت و حتی طولش رو گرفت
```java
 package com.exceptions;

import java.util.ArrayList;

public class Generics<T>{
    public ArrayList<T> mylist = new ArrayList<>();
    private int count;

    public void add(T value){
        mylist[count++] = value;
    }

    public T get(int count){
        return mylist[count];
    }
}

```
اینجا دیگه کد های بالا کار نمیکنن 
خب حالا iterable interface برای کمک به ما میاد 
برای اینکه از ایترابل استفاده کنیم باید از اینترفیسش استفاده کنیم 
```java
package com.emsal;


public class Main {
    public static void main(String[] args){
        var cars = new GenericList<String>();
        cars.add("no one");
        cars.add("stays the same");
        cars.add("no one");
        cars.add("stays the same");
        cars.add("no one");
        cars.add("stays the same");
        cars.add("no one");
        cars.add("stays the same");
        cars.add("no one");
        cars.add("stays the same");
//        var iterator = cars.iterator();
        for (String car : cars){
            System.out.println(car);
        }

}}

```

```java
package com.emsal;


public class Main {
    public static void main(String[] args){
        var cars = new GenericList<String>();
        cars.add("no one");
        cars.add("stays the same");
        cars.add("no one");
        cars.add("stays the same");
        cars.add("no one");
        cars.add("stays the same");
        cars.add("no one");
        cars.add("stays the same");
        cars.add("no one");
        cars.add("stays the same");
        var iterator = cars.iterator();

        while (iterator.hasNext()){
            String current = iterator.next();
            System.out.println(current);
        }
    }

}
```
توی این اگه به اندازه خوده لیست ما اعضا نداشته باشیم null برمیگردونه 
پس حلقه for هم از ایتریبل استفاده میکنه 
اگه implements Iterable رو حذف کنیم خواهیم دید که توی مین مینویسه 
for each not applicable to type GenericList
پس اگه خواستیم تایپ لیست رو عوض کنیم بعدا خواهیم دید که مشکلی برخورد نمیکنه چون ما اینترفیس رو صدا زدیم 
در ادامه متد iterator رو پیاده سازی کنیم چون الان داره null برمیگردونه 
این متد Iterable رو برمیگردونه که از کتابخونه java.util هست پس حالا باید کلاس جدیدی درست کنیم که iterator interface رو برمیگردونه 


```java
package com.emsal;

import java.util.Arrays;
import java.util.Iterator;

public class GenericList<T> implements Iterable<T> {
    private T[] item = (T[])new Object[10];
    private int count;
    public void add(T value){
        item[count++] = value;
    }

    public T get(int index){
        return item[index];
    }
    @Override
    public Iterator<T> iterator() {
        return new ListIterator(this);
    }

    private class ListIterator implements Iterator<T> {
        private GenericList<T> list;
        private int index;
        public ListIterator(GenericList<T> list){
            this.list = list;
        }

        @Override
        public boolean hasNext() {
            return (index < list.count);
        }

        @Override
        public T next() {
            return list.item[index++];
        }
    }ها کار داریم 
}
```
لازم نیست که تک تکه اینا رو حفظ کنی مهم اینکه کلیاتشو بفهمی و بدونی که چه کارایی میشه باهاشون کرد
#### collections
کلی پیاده سازی داره که اکثر مواقع ما با ArrayList 
```java
package com.emsal;

import java.util.ArrayList;
import java.util.Collection;

public class CollectionDemo {
    public static void show(){
        Collection<String> collection = new ArrayList<>();
        collection.add("A");
        collection.add("B");
        collection.add("C");
        System.out.println(collection);
    }
}
```
ما توی این کد میتونیم آیتم ها رو با حلقه ببینیم و حتی میتونیم که تمام آیتم ها رو یک جا وارد کنیم به جای اینکه دونه دونه اونها رو وارد کنیم 
```java
package com.emsal;

import java.util.ArrayList;
import java.util.Collection;
import java.util.Collections;

public class CollectionDemo {
    public static void show(){
        Collection<String> collection = new ArrayList<>();
        Collections.addAll(collection, "A","B","c");
        System.out.println(collection);
    }
}
```
ما میتونیم همچنین سایزشونم برگردونیم 
```java
	System.out.println(collection.size());
```
میتونیم از کالکشن چیزی رو پاک کنیم 
```java
	collection.remove("A");
	collection.clear();
	collection.isEmpty();
```
حتی میتونیم چک کنیم که آیا مقداری رو داره یا نه
```java
	System.our.println(collection.contains("A"));
```
اگه خواستی که کالکشن رو توی آرایه معمولی ذخیره کنی 
```java
	Object[] objectarray =  collection.toArray();
```
اون وقت وقتی این رو میخوای صدا بزنی اینطور collection. گزینه هایی رو میاره که برای آبجکت ها وجود دارن اگه خواستی که آرایه مثلا به تایپ استرینگ باشه میتوین اینطوری ادامه بدی:
```java
	String[] stringArray = collection.toArray();
```
برای مقایسه هم که میدونی اگه بخوای دوتا آبجکت رو همینطوری با == مقایسه کنی فالس میده ولی با استفاده از collection.equals() اوکی میشه مشکلمون 
#### list interfaces
توی این مورد ما ایندکس داریم و میتونیم با ایندکس ها به ایتم ها دسترسی داشته باشیم و به اونها رو اضافه یا عوض ویا تغییر بدیم 

ما یک متد اورراید شده داریم به نام ادد که میتونیم بهشون ایندکس بدیم و ولیو هم بهشون بدیم 
```java
        List<String> lst = new ArrayList();
        lst.add("hey");
        lst.add("there you");
        lst.add(0,"I seem depresed");
        System.out.println(lst);
```
```java
        List<String> lst = new ArrayList();
        Collections.addAll(lst,"A", "B", "C");
        System.out.println(lst);
```
```java
package com.emsal;

import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

public class CollectionDemo{
    public static void show(){
        List<String> lst = new ArrayList();
        Collections.addAll(lst,"A", "B", "C");
        System.out.println(lst.get(0));
    }
}
```
```java
        List<String> lst = new ArrayList();
        Collections.addAll(lst,"A", "B", "C");
        System.out.println(lst.get(0));

```
```java
	Collections.addAll(lst,"A", "B", "C", "A");
        System.out.println(lst.indexOf("A"));
	0
```
```java
	Collections.addAll(lst,"A", "B", "C", "A");
	System.out.println(lst.lastIndexOf);
	3
```
```java
	System.out.println(lst.subList(0,2));
```

### compairable interface
توی این ویدیو یاد خواهیم گرفت که چجوری داده ها رو سورت کنیم توی و مقایسه کنیم اونها رو با هم دیگه 
خیلی از الگوریتم های sort از compairable ارث بری میکنن
```java
package com.emsal;

import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

public class Main {
    public static void main(String[] args){
        List<Customer> customers = new ArrayList<>();
        customers.add(new Customer("C"));
        customers.add(new Customer("A"));
        customers.add(new Customer("B"));
        Collections.sort(customers);
        System.out.println(customers);

    }
}
```
اینجا اگه بخوایم مقایسه کنیم میگه که باید از comparable ارث بری کنه برای همین باید این قسمتش رو اوکی کنیم برای همین داریم:
```java
package com.emsal;

public class Customer implements Comparable<Customer>{
    private String name;

    public Customer(String name){
        this.name = name;
    }

    @Override
    public int compareTo(Customer other) {
        return (name.compareTo(other.name));
    }

    @Override
    public String toString(){
        return name;
    }
}
```
توی کامپریبل اگه یادت باشه جواب ها باید به این صورت باشه که اگه منفی باشه یعنی کوچک تر هست اگه صفر باشه یعنی مساوی و اگه بزرگتر باشه عدد مثبت برمیگردونه 
#### comparator interface
کد قبلی مشکلی که داره این هست که فلکس ابل نیست اگه خواستیم چیزه بزاریم برای سورت کردن به مشکل بر میخوریم
مثلا فرض کن که یوزر ها ایمیل هم دارن اگه بخوایم که اونها رو بر این اساس سورت کنیم 
ی کامپراتور درست میکنیم و بعد شیوه مقایسه رو میزاریم بعدش وقتی که پیاده سازی انجام شد خواهیم دید که متد sort اورلود هست و چند تا پیاده سازی براش هست از اونی استفاده میکنیم که بتونیم ماله خودمون رو اضافه کنیم 
```java
package com.emsal;

import java.util.Comparator;

public class EmailComprator implements Comparator<Customer> {


    @Override
    public int compare(Customer o1, Customer o2) {
        return o1.getEmail().compareTo(o2.getEmail());
    }
}
```
```java
package com.emsal;

public class Customer implements Comparable<Customer>{
    private String name;
    private String email;

    public Customer(String name, String email){
        this.name = name;
        this.email = email;
    }

    @Override
    public int compareTo(Customer other) {
        return (name.compareTo(other.name));
    }

    @Override
    public String toString(){
        return name;
    }

    public String getEmail(){
        return email;
    }
}
```
```java
package com.emsal;

import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

public class Main {
    public static void main(String[] args){
        List<Customer> customers = new ArrayList<>();
        customers.add(new Customer("C","e5"));
        customers.add(new Customer("Abra", "e4"));
        customers.add(new Customer("B", "e3"));
        customers.add(new Customer("Ali", "e2"));
        Collections.sort(customers);

        System.out.println(customers);
        Collections.sort(customers,new EmailComprator());
        System.out.println(customers);
    }
}
```
توی سورت دومی گزینه ای هست که میتونیم اونطور که میخوایم سورت کنیم 
#### Queue interface
وقتی از کیو ها استفاده میکنیم که میخوایم کار ها به صورتی انجام بگیرن که وارد شدن بیشتره صف هایی که ممکنه توی کله کارت ازشون استفاده کنی ArrayDeque و proiorityQueue هست 
deque مختصر برای double ended queue
یعنی اینکه میتونیم اخر و اول صف رو چیزی بزاریم و یا چیزی رو حذف کنیم 
پراروریتی برای هر عضو یک اولویت دارن 
```java
package com.emsal;

import java.util.ArrayDeque;
import java.util.Deque;

public class DeQueueDemo {
    public static void show(){
        Deque<String> queue = new ArrayDeque<>();
        queue.add("till");
        queue.add("I collapse");
        queue.offer("i");
        
    }
}
```
افر در اینجا به این معنا هست که اگه مثلا محدودیت داشتیم و صف پر بود ما افر میدیم ولی نمیاد توی صف
```java
	queue.peek();
	queue.element();
```
پیک اولی رو نشون میده ولی اگه که صف خالی بود اون وقت میاد و نال نشون میده ولی المنت ارور میده 
```java
	queue.poll();
	queue.remove();
```
این برای پول و ریمو هم همینطوره پول اگه لیست خالی بود نال میده ولی ریمو ارور میده 
#### set interface
نان اوردری هست و نان دوپلیکید 
```java
        Set<String> maset = new HashSet<>();
        maset.add("a");
        maset.add("B");
        maset.add("e");
        System.out.println(maset);
```
ما میتونیم همچنین کالکشن ها رو برای داپلیکید رو بگیریم ازش تبدیل کنیم به ست
```java
        Collection<String> collection = new ArrayList<>();
        Collections.addAll(collection, "A" , "B", "A", "A");
        System.out.println(collection);
        Set<String> set = new HashSet<>(collection);
        System.out.println(set);
```

ویژگی هایی که ست ها دارن :
1. احتماع / union
```java
        Set<String> set1 = new HashSet<>(Arrays.asList("a", "b"));
        Set<String> set2 = new HashSet<>(Arrays.asList("d", "c"));
        set1.addAll(set2);
        System.out.println(set1);
```
2. احتماع / intersection
```java
        Set<String> set1 = new HashSet<>(Arrays.asList("a", "b"));
        Set<String> set2 = new HashSet<>(Arrays.asList("d", "c" , "b"));
        set1.retainAll(set2);
        System.out.println(set1);
```
3. تفاوت / difference
```java
	        set1.removeAll(set2);
```

#### hash tables 
فرض کن که یه لیست یک میلیون یداری از کاربرا و میخوای ببینی که توی اون لیست کاربری هست که لیسته خاصی داشته باشه درش یا نه اینجا مشکل ما همون O(n) هست یک میلیون هست برای حل این مشکل ها ما از مپ ها استفاده میکنیم یا هش تیبل ها که همون دیکشنری های ما هستن 
هش تیبل ها در پیاده سازی دیکشنری ها استفاده شدن 
#### map interfaces

```java
        var c1 = new Customer("a","e1");
        var c2 = new Customer("b", "e2");
        Map<String, Customer> map = new HashMap<>();
        map.put(c1.getEmail(),c1);
        map.put(c2.getEmail(),c2);
        var customer = map.get("e1");
        System.out.println(customer);
        var customer1 = map.get("e10");
        System.out.println(customer1);
        var customer2 = map.getOrDefault("ep1", new Customer("unknown",""));
        System.out.println(customer2);
        map.replace("e1", c1, new Customer("c", "e22222222"));
        System.out.println(map.get("e1"));
        System.out.println("\n\n\n");
        for (var values: map.values()){// it's collection object
            System.out.println(values);
        }
        System.out.println("\n\n\n");
        for (var value: map.keySet()){//  it's a set object
            System.out.println(value);
        }
        System.out.println("\n\n\n");
        for (var value : map.entrySet()){// it's a entry object 
            System.out.println(value);
        }
```


