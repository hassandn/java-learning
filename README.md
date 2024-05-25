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


### lambda expressions 
توی این بخش درمورد فانکشنال پروگرمنیگ میگه 
#### functional interface
an interface with a single abstract method
مثلا کامپریبل تنها یک متد compateTo این فانکشنال اینترفیس هست 
دیفالت متد در اینترفیس ها پیاده سازی دارن

```java
package hassandn.com;

public class Main {
    public static void main(String[] args){
        greet(new Console());
    }
    public static void greet(Printer printer){
        printer.print("Hello World");
    }
}
package hassandn.com;

public interface Printer {
    void print(String message);
}
package hassandn.com;

public class Console implements Printer{
    @Override
    public void print(String message) {
        System.out.println(message);
    }
}
```
description for later

ما همچنین دیفالت متد داریم توی اینتفرفیس ها که میتونیم کد بزنیم و پیاده سازی داشته باشیم توی اینتر فیسمون 
تا وقنی که ابسترک متد یکی بیشتر نداشته باشیم توی اینترفیس ما اون رو به صورت فانکشنال اینترفیس میشناسیم
#### anonymous inner class
بعضی وقتا ما به صراحت نمیخوایم پیاده سازی ر وانجام بدیم و در اصل میخوام که پیاده سازی رو برای یک جای خاص و فقط یک بار از اون استفاده کنیم و نخوایم جای دیگه از اون استفاده کنیم
اینها انانیموس هستن چون اسم ندارن ما اونها رو اینر کلاس میگیم چون داخل متد از اون ها استفاده میکنیم و فقط پیاده سازی هستن برای استفاده از اونها کافیه که اینفترفیس رو صدا بزنیم و همونجا پیاده سازی رو انجام بدیم اما توی جاوا 8 تابع های لامبدا اومدن که کار رو حتی راحت تر میکنن
```java
package hassandn.com;

public class Main {
    public static void main(String[] args){
        greet(new Printer() {
            @Override
            public void print(String message) {
                System.out.println("hello" + message);
            }
        });
    } 
    public static void greet(Printer printer){
        printer.print("Hello World");
    }
}
```
این دقیقا کاری میکنه که پیاده سازی قبلی انجام داده
#### lambda Expresions
لامبدا اکسپرشن ها آبجکت هستن ولی ما میتونیم از اونها به عنوان انانیموس فانکشن استفاده کنیم 
خب پیاده سازی ای که داریم 
```java
package hassandn.com;

public class Main {
    public static void main(String[] args){
        greet(message -> System.out.println(message));
        
    }
    public static void greet(Printer printer){
        printer.print("Hello World");
    }
}

```
پیاده سازیش به این صورته ما پارامتر رو مینویسم و بعدش با این علامت -> پیاده سازی رو داریم این چون ما یکی پارامتر داریم نیازی به اعلان نیست البته اگه هم نوع رو نزاریم قرار نیست به مشکلی بخوریم چون میدونه که از کجا داره استفاده میکنه و خودش تایپ رو چک میکنه 

```java
        greet((String message) -> System.out.println());
```
برای آرگیومنت ها ما میتونیم میتونیم از پرانتز استفاده کنیم و برای پیاده سازی باید از پرانتز های خم استفاده کنیم 
یکی از فرق های انانیموس و لامبدا اینکه توی انانیموس ها میتونی استیت بزاری و وقتی توی انانیموس ها از کلمه this استفاده کنیم به خوده اینتستنس خوده همون متد دسترسی داریم در حالیکه در لامبدا ما به استیت هایی که توی خوده کلاس هستن دسترسی داریم 
و اینکه لامبدا استیت نداره خودش و میتونه از استیت های کلاسیی که توش هست استفاده کنه 
#### method refrences
این برای این هست که از متد های لمبدا راحت تر بتونیم استفاده کنیم و بدون اینکه پارامتر رو بنویسیم بتونیم فقط متد رو بنویسیم 
```java
        greet(System.out::println);
```
اینون به این صورت مینویسیم 
```java
package hassandn.com;

public class Main {
    public static void print(String message){

    }
    public static void main(String[] args){
        greet(Main::print);
    }
    public static void greet(Printer printer){
        printer.print("Hello World");
    }
}
```
کد بالا به این صورت هست که میتونیم یک تابع دیگه رو صدا بزنیم حالا اگه تابع ما اینستنس بود خواهیم داشت 
```java
package hassandn.com;

public class Main {
    public void print(String message){

    }
    public static void main(String[] args){
        Main demo = new Main();
        greet(demo::print);
    }
    public static void greet(Printer printer){
        printer.print("Hello World");
    }
}
```
اینجا یک اینستنس ازش میسازیم و ادامه میدیم 
اگه خواستیم برای کانستراکتور چیزی اضافه کنیم خواهیم داشت :
```java
	greet(message -> new Main(message));
	greeet(Main::new)
```

ما چهار نوع فانکشنال اینتفرفیس 
1.consumer -> takes a single argument and returns no results => void consume(obj)
2.supplier -> opisite of consumer interface it represent action that need no argument and returns a value => obj supply() 
3.Fuction -> can map a value to another value => obj map(obj)
4.Predicate -> it tests values => bool test(condition)
# auto boxing چه بود و چه کرد 
imperative programming
declarative programming
ایمپرتیو میگه که داستان برنامه چجوری باید باشه برای مثال کجا ایف باشه کجا لوپ و... 
ولی دکلرتیو میگه که چیزی باید انجام بشه مثل اس کیو ال که میگه سلکت کن فلان چیزو از فلان جا 
پس ایمپرتیو میگه که چه جوری انجام بشه دکلرتیو میگه که چی باید انجام بشه 
### مثال برای کانسیومر به این صورت هست که:
فرض کن که یک لیست داریم برای این لیست میتونیم ایمپرتیو پیش بریم که خودمون فلوی کار رو نشون بدیم و یا میتوینم از دکلرتیو پیش بریم که بگیم چه کاری باید انجام بشه  
```java
package hassandn.com;

import java.util.List;

public class Main {
    public static void main(String[] args){
        List<Integer> malist = List.of(1,3,2);
        
        // imperative programming
        for (var item: malist){
            System.out.println(item);
        }
        
        // declarative programming
        malist.forEach(item -> System.out.println(item));
    }
}
```

### chaining concumer 
برای اینکه یک سری کار ها رو انجام بدیم با کانسیومتر ها متدی داره به نام andThen() که میتونی از اون استفاده کنی و یک سری از کار ها رو به صورت زنجیره ای استفاده کنی
```java
    public static void main(String[] args){
        List<String> list = List.of("a", "b" ,"c");
        Consumer<List> print = item -> System.out.println(item);
        Consumer<List> printUpperCase = item -> System.out.println(item);
    }
```
#### supplier interface
```java
package hassandn.com;

import java.util.function.Supplier;

public class Main {
    public static void main(String[] args){
        Supplier<Double> getRandom = () -> Math.random();
        var rndm = getRandom.get();
        System.out.println(rndm);
    }
}
```
دلیل اینکه ما دیتا رو میریزیم توی rndm این هست که این یه چیزی رو ریترن میکنه و باید ی جا ذخیره باشه (right?)
#### lazy evaluation 
یعنی صدا زدن تابع وقتی که به اون نیاز داریم این دستور جنریت نمیشه تا وقتی که ما به صورت واضح بگیم که چیکار میخوایم بکنیم 
#### functional interface
ما انواع مختلفی داریم برای فانکشنال اینترفیس بایفانکشنال داریم و ...
مثلا ما intFunction داریم که ولیو از جنس اینت میگیره و ولیو ای به جنس r ریترن میکنه 
```java
package hassandn.com;

import java.util.function.Function;
import java.util.function.Supplier;

public class Main {
    public static void main(String[] args){
        Function<String, Integer> length = value -> value.length();
        var len = length.apply("hi");
        System.out.println(len);
    }
}
```
```java
package hassandn.com;

import java.util.function.Function;
import java.util.function.IntFunction;
import java.util.function.Supplier;

public class Main {
    public static void main(String[] args){
        Function<String, Integer> length = value -> value.length();
        var len = length.apply("pursuit of happiness");
        System.out.println(len);
        IntFunction<Integer> test = (vale) -> vale * vale;
        var result = test.apply(6);
        System.out.println(result);
    }
}
```
declerative programming
دو راه وجود داره برای اینکه به ترتیب کار ها رو انجام بدیم یکی این هست که از andThen استفاده کنیم و راه دیگش این هست که از compose استفاده کنیم که فرقی ندارن فقط ترتیب کامپوز برعکسه
#### composing 
```java
package hassandn.com;


import java.util.function.Function;

public class Main {
    public static void main(String[] args){
        //=
        Function<String, String> replaceWithEqual = value -> value.replace(":","=");
        // {
        Function<String, String> addCurlyBraces = value -> "{" + value + "}";

        var restult = replaceWithEqual.andThen(addCurlyBraces).apply("key:value");
        System.out.println(restult);
        var result = replaceWithEqual.compose(addCurlyBraces).apply("key:value");
        System.out.println(result);
    }
}
```
این کد دو روش رو نشون داده برای اجرا کردن کد
دکلرتیو پروگرمنیگ یعنی که فقط بگی چه کاری میخوای انجام بشه و پیاده سازیش رو کاری نداشته باشی
#### predicate interface
ما از اینها استفاده میکنیم برای فیلتر کردن دیتا 
```java
package hassandn.com;


import java.util.function.Function;
import java.util.function.Predicate;

public class Main {
    public static void main(String[] args){
        Predicate<String> checklenBiggerThan5 = str -> str.length()>5;
        var result = checklenBiggerThan5.test("sly33333");
        System.out.println(result);
    }
}
```
حالا میمونه کارکردن با تست های پیچیده ما میتونیم پردیکیت ها رو با هم قاطی کنیم تا تست های بهتری داشته باشیم 
ما and or negate داریم 
```java
package hassandn.com;


import java.util.function.Function;
import java.util.function.Predicate;

public class Main {
    public static void main(String[] args){
        Predicate<String> hasRightBrace = (value) -> value.startsWith("{");
        Predicate<String> hasLeftBrace  = (valye) -> valye.endsWith("}");
//        var result = hasLeftBrace.negate(hasRightBrace).test("{key:value");
        var result = hasLeftBrace.negate().test("key:value}");
        System.out.println(result);

    }
}

```
operands -> x y
operator -> +
x+y

#### binaryOperator Interface
مثال: میخوای دوتا عدد رو جمع کنی و بعد اونها رو مربع کنی
```java
        BinaryOperator<Integer> add = (a,b) -> a + b;
        Function<Integer, Integer> square = (a) -> a * a;
        var result = add.andThen(square).apply(2,1);
        System.out.println(result);
```
#### Unary Interface

برای متد هایی هست که یک کار رو انجام میدن 
```java
        UnaryOperator<Integer> increment = x -> x + 1;
        UnaryOperator<Integer> squar = x -> x*x;
        var result = increment.andThen(squar).apply(1);
        System.out.println(result);
```
# streams
یکی از فیچر های جاوا هست که اجازه میده از کالکشن ها در دکلرتیو استفادشون کنیم 
استریم ها اومدن که کمک کنن فلوی برنامه به صورت دکلرتیو باشه به صورت فانکشنال باشه 
استریم ها برای استفاده از کالکشن ها هستن کالکشن ها مثل منبع هستن و استریم ها مثل لوله ها هستن که از اون منبع کشیده میشن و این کار به صورت دکلرتیو هست 
```java
package hassandn.com;

public class Movies {
    private String name;
    private int likes;
    public Movies(String name,
                  int likes)
    {
        this.name = name;
        this.likes =likes;
    }
    public int getLikes(){
        return likes;
    }
}
package hassandn.com;


import java.util.List;

public class Main {
    public static void main(String[] args){
        List<Movies> movies = List.of(
                new Movies("a",10),
                new Movies("b", 12),
                new Movies("c", 15)
                );
        // imperative programming(how something should be done)
        int counter = 0;
        for (var items : movies){
            if (items.getLikes()>10){
                counter ++;
            }
        }
        System.out.println(counter);

    }
}
        // Declarative programming(Functional)(what should be done)
        var result = movies.stream().filter(movie -> movie.getLikes() > 10).count();
        System.out.println(result);

```
راه های زیادی وجود داره برای پیاده سازی استریم ها 
1. کالکشن ها
2. آرایه ها
3. آبجکت های دلخواه
4. استریم های نامحدود و محدود
stream.generate برای روند های بی نهایت هست
stream.iterator هم برای همین هست
مثال استفاده استریم برای کالکشن ها :
```java
	Collection<Integer> x;
	x.stream();
```
این میگه که هر کلاسی که از کالشن ها ارث بری میکنه میتونه از استریم ها استفاده کنه برای همین میتونیم ArrayList درست کنیم 
```java
	var list = new ArrayList<>();
	list.stream();
```
ما برای آرایه ها هم میتونیم استفاده کنیم فقط به طور مستقیم نه و باید از کلاس Array استفاده کنیم 
```java
 int[] numbers = {1, 2, 3};
 Arrays.stream(numbers).forEach(n -> System.out.println(n));
```
میتونیم از varargs هم استفاده کنیم 
```java
	Stream.of(1, 2, 3);
```
ما همچنین میتونیم از استریم های بی نهایت استفاده کنیم کلی راه هست برای انجام دادنش ما متونیم از جنریت استفاده کنیم 
```java
	var stram = Stream.generate(() -> Math.random());
	stream.limit(4).forEach(n -> System.our.println(n));
```
این کد به صورت بینهایت استریم میسازه با عدد های رندوم ما اینکار رو نمیتونیم با کالکشن ها بکنیم چون اگه بخوایم انجام بدیم مموریمون فول میشه 
lazy evaluation یعنی کد رو نوشتیم ولی هر وقت که نیازش داشتیم صداش میزنیم 
خطه دومه کده بالا به صورت بینهایت این کار رو انجام میده ولی برای اینکه کاری کنیم که به محدودیت نرسه از limit استفاده میکنیم 
ی روش دیگه ای هم هست که بخوایم این کار رو انجام بدیم ایتریتور 
```java
	Stream.iterator(1, n -> n+1).limit(3).forEach(n -> System.out.prinltn(n));
	
```
فانکشنال پروگرامنیگ نوعی از دکلرتیو پروگرامینگ هست که با صدا زدن اسم تابع فقط میگیم که چه کاری باید انجام بشه 
هر کالکشنی در جاوا متدی به نام استریم داره که اون استریم های آبجکت برمیگردونن
```java
package hassandn.com;


import java.util.List;
import java.util.stream.Stream;

public class Main {
    public static void main(String[] args){
        List<Movies> movie = List.of(
                new Movies("a",2),
                new Movies("b", 13),
                new Movies("c", 14)
        );

        var count = movie.stream().filter(item -> item.getLikes() > 12).count();
        System.out.println(count);
    }
}
```
ما میتونیم داده ها رو در استریم ها ذخیره کنیم دو راه برای این کار وجود داره یکی استفاده از استریم.جنریت هست 
```java
        var stream = Stream.generate(() -> Math.random());
        stream.limit(5).forEach(n -> System.out.println(n));
```
ما یک راه دیگه هم داریم به نام ایترریت متد 
```java
        Stream.iterate(1,n-> n +1).limit(1_400_000).forEach(n -> System.out.println(n));
```
#### mapping elements
مپینگ یعنی دو تا نوع داده رو برداریم و یکیشون کنیم و یک نوع داده جدید بدست بیاریم 
```java
package hassandn.com;


import java.util.List;

public class Main {
    public static void main(String[] args){
        var movies = List.of(
                new Movies("A", 10),
                new Movies("B", 20),
                new Movies("C", 30)
        );
        movies.stream().map(mov -> mov.getName()).forEach(name -> System.out.println(name));
    }
}
```
ی مبحث دیگه داریم به نام فلت مپ که دوتا مجموعه جدا رو میتونی یکی کنی 
```java
package hassandn.com;


import java.util.List;
import java.util.stream.Stream;

public class Main {
    public static void main(String[] args){
        var strm = Stream.of(List.of(1, 2, 3),List.of(4, 5, 6));
        strm.forEach(list -> System.out.println(list));
    }
}
[1, 2, 3]
[4, 5, 6]
```

```java
package hassandn.com;


import java.util.List;
import java.util.stream.Stream;

public class Main {
    public static void main(String[] args){
        var strm = Stream.of(List.of(1, 2, 3),List.of(4, 5, 6));
        strm.flatMap(list -> list.stream())
        .forEach(list -> System.out.println(list));
    }
}
1
2
3
4
5
6
```
ما چند دو نوع استریم داریم 
intermediate streams -> It return a new stream / map() filter()
terminal streams -> forEach()
اینترمیدیت میاد و این شکلی میشه که یک استریم جدید درست میکنه و تا اینکه اون رو در ترمینال صدا نزنیم اجرایی نمیشن برای مثال داریم :
```javapackage hassandn.com;


import java.util.List;

public class Main {
    public static void main(String[] args){
        var movie = List.of(
                new Movies("A", 12),
                new Movies("B", 15),
                new Movies("C", 25)
        );

        movie.stream()
                                            .filter(m -> m.getLikes() > 12).count();
    }
}
```	
اینجا هیچ اتفاقی نمیوفته تا وقتی که فور ایچ رو براشون صدا میزنیم 
```java
package hassandn.com;


import java.util.List;

public class Main {
    public static void main(String[] args){
        var movie = List.of(
                new Movies("A", 12),
                new Movies("B", 15),
                new Movies("C", 25)
        );
        movie.stream()
                .filter(m -> m.getLikes() > 12)
                .forEach(n -> System.out.println(n.getName()));
    }
}
```
ما میتونیم این کد رو مختصر تر بنویسم و یک قسمتش رو کوتاه تر بنویسیم از اونجایی که فیلتر داخل پرانتز یک پریدیکیت میگیره برای همین داریم : 
```java
package hassandn.com;


import java.util.List;
import java.util.function.Predicate;

public class Main {
    public static void main(String[] args){
        var movie = List.of(
                new Movies("A", 12),
                new Movies("B", 15),
                new Movies("C", 25)
        );
        Predicate<Movies> checkLikes = m -> m.getLikes() > 12;
        movie.stream()
                .filter(checkLikes)
                .forEach(n -> System.out.println(n.getName()));
    }
}
```
#### slicing streams
ما چهار نوع اسلاسینگ استریم داره 
1. limit()
2. skip() -> Its good for pagenation
3. takeWhile(Predicate)
4. dropWhile(Predicate)
اسکیپ برای پجینیشن استفاده میشه که مثلا کد رو طوری بنویسی که مثلا پیج فلان n تا رو رد کنه البته باید لیمیت هم بزاریم
فرق دراپ وایل و لیمیت اینکه لیمیت کله دیتا رو بررسی میکنه دراپ وایل وقتی شرط رفت استاپ میکنه
```java
package hassandn.com;


import java.util.List;

public class Main {
    public static void main(String[] args){
        var movie = List.of(
                new Movies("A", 12),
                new Movies("D", 56),
                new Movies("B", 15),
                new Movies("C", 25)
        );
        movie.stream()
                .limit(2)
                .filter(n -> n.getLikes() > 12)
                .forEach(n -> System.out.println(n.getName()));
        System.out.println();
        System.out.println(1);
        System.out.println();
        movie.stream()
                .skip(2)
                .forEach(n -> System.out.println(n.getName()));
        System.out.println();
        System.out.println(2);
        System.out.println();
        movie.stream()
                .takeWhile(n -> n.getLikes() >15)
                .forEach(n -> System.out.println(n.getName()));
        System.out.println();
        System.out.println(3);
        System.out.println();
        movie.stream()
                .dropWhile(n -> n.getLikes() >80)
                .forEach(n -> System.out.println(n.getName()));
    }
}
```
####  sorting streams
برای سورت کردن دو تا راه داریم اولی اینکه توی خوده کلاسه یک متد داشته باشیم که خودش مقایسه کنه و دومی اینکه یک متد لامبدا بنویسیم
اولین روش به این صورت هست که :
```java
package hassandn.com;

public class Movies implements Comparator {
    private String name;
    private int likes;
```
و بعد پیاده سازی متد رو انجام میدیم
ی راهه دیگش اینکه یک لامبدا درست کنیم که داریم:
```java
package hassandn.com;


import java.util.List;

public class Main {
    public static void main(String[] args){
        var movie = List.of(
                new Movies("C", 12),
                new Movies("D", 56),
                new Movies("B", 15),
                new Movies("A", 25)
        );
        movie.stream()
                .sorted((a, b) -> a.getName().compareTo(b.getName()))
                .forEach(n -> System.out.println(n.getName()));
    }
}
```
ی راه ساده ترم هست برای نوشتن این که میگه:
یک متد استاتیک هست توی اینترفیس کامپریتور
```java
package hassandn.com;


import java.util.Comparator;
import java.util.List;

public class Main {
    public static void main(String[] args){
        var movie = List.of(
                new Movies("C", 12),
                new Movies("D", 56),
                new Movies("B", 15),
                new Movies("A", 25)
        );
        movie.stream()
//                .sorted((a, b) -> a.getName().compareTo(b.getName()))
                .sorted(Comparator.comparing(Movies::getName))
                .forEach(n -> System.out.println(n.getName()));
    }
}
```
#### Getting unique Elements
فرض کن که ما به جای لایک ها قیمت فیلم ها رو داریم برای همین داریم میخوام کلا قیمت ها رو ببینیم و برامون مهم نیست که چه تعداد از اون قیمت ها رو داریم برای همین خواهیم داشت
```java
package hassandn.com;


import java.util.Comparator;
import java.util.List;

public class Main {
    public static void main(String[] args){
        var movie = List.of(
                new Movies("C", 12),
                new Movies("D", 56),
                new Movies("B", 15),
                new Movies("A", 25),
                new Movies("a", 25)
        );
        movie.stream()
                .map(Movies::getLikes)
                .distinct()
                .forEach(System.out::println);
    }
}

12
56
15
25
```
طوری که نوشتم متد پرینت رو میگن بهش متد رفرنس
#### peeking Elements
این برای ترابل شوتینگ مناسبه چون میتونی وسط استریم اونها رو قرار بدی و فلوی کارتو چک کنی برای مثال داریم:
دلیل اینکه نمیتونیم از forEach برای این کار استفاده کنیم این هست که فورایچ ترمینال هست 
#### Reducers	
##### Simple Reducers
```java
package hassandn.com;


import java.util.Comparator;
import java.util.List;

public class Main {
    public static void main(String[] args){
        var movie = List.of(
                new Movies("C", 12),
                new Movies("D", 56),
                new Movies("B", 15),
                new Movies("A", 25),
                new Movies("a", 25)
        );
        var result = movie.stream()
                .anyMatch(m -> m.getLikes() > 49);
        System.out.println(result);
    }
}
```
```java
package hassandn.com;


import java.util.Comparator;
import java.util.List;

public class Main {
    public static void main(String[] args){
        var movie = List.of(
                new Movies("C", 12),
                new Movies("D", 56),
                new Movies("B", 15),
                new Movies("A", 25),
                new Movies("a", 25)
        );
        var result = movie.stream()
                .allMatch(m -> m.getLikes() > 49);

        System.out.println(result);

    }
}

```
```java
package hassandn.com;


import java.util.Comparator;
import java.util.List;

public class Main {
    public static void main(String[] args){
        var movie = List.of(
                new Movies("C", 12),
                new Movies("D", 56),
                new Movies("B", 15),
                new Movies("A", 25),
                new Movies("a", 25)
        );
        var result = movie.stream()
                .noneMatch(m -> m.getLikes() > 100);

        System.out.println(result);
    }
}
```
```java
package hassandn.com;


import java.util.Comparator;
import java.util.List;

public class Main {
    public static void main(String[] args){
        var movie = List.of(
                new Movies("C", 12),
                new Movies("D", 56),
                new Movies("B", 15),
                new Movies("A", 25),
                new Movies("a", 25)
        );
        var result = movie.stream()
                .findFirst().get();

        System.out.println(result.getName());
    }
}
```
```java
package hassandn.com;


import java.util.Comparator;
import java.util.List;

public class Main {
    public static void main(String[] args){
        var movie = List.of(
                new Movies("C", 12),
                new Movies("D", 56),
                new Movies("B", 15),
                new Movies("A", 25),
                new Movies("a", 250)
        );
        var result = movie.stream()
                .max(Comparator.comparing(Movies::getLikes))
                .get();

    }
}
```
توی این کد میاد و بر اساس تعداد لایک ها مقایسه میکنه و اونیکه بیشتره رو نشون میده 
##### Reduceing a Stream
فرض کن که میخوای تعداد لایک های همه فیلم ها رو بشماریم اینطور خواهیم داشت:
```java
package hassandn.com;


import java.util.Comparator;
import java.util.List;

public class Main {
    public static void main(String[] args){
        var movie = List.of(
                new Movies("C", 12),
                new Movies("D", 56),
                new Movies("B", 15000),
                new Movies("A", 25),
                new Movies("a", 250)
        );
        var result = movie.stream()
                .map(m -> m.getLikes())
                .reduce((a,b) -> a+b);
        System.out.println(result.orElse(3));
    }
}
```
کلاس آپشنال یک آبجکتی رو برمیگردونه که شاید ولیو ای رو برنگردونه برای همین ما یک دونه چیز پیشفرض براش میزاریم
ما میتونیم همچنین اینطوری این رو بنویسیم
```java
                .reduce(Integer::sum);
```
حتی میتونیم برای اینکه اور الس نزاشته باشیم میتونیم از دستور زیر استفاده کنیم 
یک مدل دیگه هم داره که یک ایدندیتی داره که میتونیم با استفاده از اون از اور الس استفاده نکنیم و همینطور فقط مشخص کنیم که چه چیزی بزاره که این همون بالایی هست که اورراید شده فقط
#### collectors
وقتی میخوای که دیتایی که داره استریم میاد داخل یک ساختار داده ثبت بشه خواهیم داشت
```java
package hassandn.com;


import java.util.Comparator;
import java.util.List;
import java.util.stream.Collectors;

public class Main {
    public static void main(String[] args){
        var movie = List.of(
                new Movies("C", 12),
                new Movies("D", 56),
                new Movies("B", 15000),
                new Movies("A", 25),
                new Movies("a", 250)
        );
        var result = movie.stream()
                .filter(m -> m.getLikes() >234)
                .map(m -> m.getName())
                .collect(Collectors.toList());
        System.out.println(result);
    }
}
```
```java
package hassandn.com;


import java.util.Comparator;
import java.util.List;
import java.util.stream.Collectors;

public class Main {
    public static void main(String[] args){
        var movie = List.of(
                new Movies("C", 12),
                new Movies("D", 56),
                new Movies("B", 15000),
                new Movies("A", 25),
                new Movies("a", 250)
        );
        var result = movie.stream()
                .filter(m -> m.getLikes() >234)
                .collect(Collectors.toMap(key -> key.getName(),value -> value.getLikes()));
        System.out.println(result);
    }
}
```
یه چیزه خیلی باحالیم که داریم سامریازینگ هست که یک خلاصه از لیستی که درست شده میگه مثلا اوریج چقدره مین چیه مکس چیه و...
```java
package hassandn.com;


import java.util.List;
import java.util.Locale;
import java.util.stream.Collectors;

public class Main {
    public static void main(String[] args){
        Locale locale = new Locale("en", "US");
        Locale.setDefault(locale);

        var movie = List.of(
                new Movies("C", 12),
                new Movies("D", 56),
                new Movies("B", 15000),
                new Movies("A", 25),
                new Movies("a", 250)
        );
        var result = movie.stream()
                .collect(Collectors.summarizingInt(m -> m.getLikes()));
        System.out.println(result);
    }
}
```
متیونیم همچنین اون ها رو به صورت یک استرینگ در بیاریم و اونها رو جوین بدیم به هم دیگه 
```java
package hassandn.com;


import java.util.List;
import java.util.Locale;
import java.util.stream.Collectors;

public class Main {
    public static void main(String[] args){
        Locale locale = new Locale("en", "US");
        Locale.setDefault(locale);

        var movie = List.of(
                new Movies("C", 12),
                new Movies("D", 56),
                new Movies("B", 15000),
                new Movies("A", 25),
                new Movies("a", 250)
        );

        var result = movie.stream()
                .filter(m -> m.getLikes() > 10)
                .map(Movies::getName)
                .collect(Collectors.joining(", "));
        System.out.println(result);
    }
}
```
این قسمته زبان و منطقه هم مهم هستش به یاد داشته باش که وقتی این رو تنظیم نکنی بعضی جاها اذیتت میکنه 

##### Grouping Elements
فرض کن که میخوای گروه بندی کنی دیتا ها رو برای اینکار لازمه که از گروپینگ المنت ها استفاده کنی
برای مثال داریم:
اول از هم باید برای فیلم ها جانر درست کنیم برای همین یک کلاس درست میکنیم به نام جانر و تایپش رو میزاریم اینام enum برای این هست که جانر ها رو عوض کنیم مثالش:
```java
enum Level {
  LOW,
  MEDIUM,
  HIGH
}
Level myVar = Level.MEDIUM;
```
در کد خودمون داریم:
```java
package hassandn.com;

public enum Genre {
    COMEDY,
    DRAMA,
    ACTION,
}
```
```java
package hassandn.com;


import java.util.List;
import java.util.Locale;
import java.util.stream.Collectors;

public class Main {
    public static void main(String[] args){
        Locale locale = new Locale("en", "US");
        Locale.setDefault(locale);

        var movie = List.of(
                new Movies("C", 12, Genre.ACTION),
                new Movies("D", 56, Genre.COMEDY),
                new Movies("B", 15000, Genre.DRAMA),
                new Movies("A", 25, Genre.ACTION),
                new Movies("a", 250, Genre.COMEDY)
        );

        var result = movie.stream()
                .collect(Collectors.groupingBy(Movies::getGenre));
        System.out.println(result);

    }
}
```
حالا ما اینجا وقتی فیلتر کردیم میتوینم 	
میتونیم حتی اون ها رو به شکل ست بزاریم:
```java
package hassandn.com;


import java.util.List;
import java.util.Locale;
import java.util.stream.Collectors;

public class Main {
    public static void main(String[] args){
        Locale locale = new Locale("en", "US");
        Locale.setDefault(locale);

        var movie = List.of(
                new Movies("C", 12, Genre.ACTION),
                new Movies("D", 56, Genre.COMEDY),
                new Movies("B", 15000, Genre.DRAMA),
                new Movies("A", 25, Genre.ACTION),
                new Movies("a", 250, Genre.COMEDY)
        );

        var result = movie.stream()
                .collect(Collectors.groupingBy(Movies::getGenre
                        ,Collectors.toSet()));
        System.out.println(result);
    }
}
```
حالا فرض کن که میخوایم این رو به صورت استرینگ بنویسم که اسم هر جانر رو با کاما از همدیگه جدا کنه
ما اینجا داریم:
```java
package hassandn.com;


import java.util.List;
import java.util.Locale;
import java.util.stream.Collectors;

public class Main {
    public static void main(String[] args){
        Locale locale = new Locale("en", "US");
        Locale.setDefault(locale);

        var movie = List.of(
                new Movies("C", 12, Genre.ACTION),
                new Movies("D", 56, Genre.COMEDY),
                new Movies("B", 15000, Genre.DRAMA),
                new Movies("A", 25, Genre.ACTION),
                new Movies("a", 250, Genre.COMEDY)
        );

        var result = movie.stream()
                .collect(Collectors.groupingBy(Movies::getGenre
                        ,Collectors.mapping(Movies::getName
                                ,Collectors.joining( ", "))));
        System.out.println(result);
    }
}
```
برای اینکه پارتیشن بندی کنیم خواهیم داشت:
مثلا فکر کن فیلم های بالای 20 تا لایک و زیره بیست لایک رو میخوای جدا کنی برای این خواهی داشت:
```java
package hassandn.com;


import java.util.List;
import java.util.Locale;
import java.util.stream.Collectors;

public class Main {
    public static void main(String[] args){
        Locale locale = new Locale("en", "US");
        Locale.setDefault(locale);

        var movie = List.of(
                new Movies("C", 12, Genre.ACTION),
                new Movies("D", 56, Genre.COMEDY),
                new Movies("B", 15000, Genre.DRAMA),
                new Movies("A", 25, Genre.ACTION),
                new Movies("a", 250, Genre.COMEDY)
        );

        var result = movie.stream()
                        .collect(Collectors.partitioningBy(m -> m.getLikes() > 20,Collectors.mapping(Movies::getName,Collectors.joining(", "))));
        System.out.println(result);

    }
}
```
##### primitive streams
این برای پریمیتیو تایپ ها هست مثل دابل اینت و ... و میتونی مثلا رنج بزاری برای اونها 
```java
package hassandn.com;


import java.util.List;
import java.util.Locale;
import java.util.stream.Collectors;
import java.util.stream.IntStream;

public class Main {
    public static void main(String[] args){
        Locale locale = new Locale("en", "US");
        Locale.setDefault(locale);

        var movie = List.of(
                new Movies("C", 12, Genre.ACTION),
                new Movies("D", 56, Genre.COMEDY),
                new Movies("B", 15000, Genre.DRAMA),
                new Movies("A", 25, Genre.ACTION),
                new Movies("a", 250, Genre.COMEDY)
        );
        IntStream.range(0, 5)
                .forEach(System.out::println);
    }
}
```
### concurrency
#### process and Thread
پراسس یک شئ از برنامه یا اپلیکیشن ماست پراسس ایمیج کده برنامه رو داره 
os میتونه در لحظه کلی پراسس رو اجرا کنه در لحظه 
ما یک ترد اصلی داریم در کد ها که میتونیم ترد های جدید برای اون ایجاد کنیم 
```java
package hassandn.com;


import java.util.List;
import java.util.Locale;
import java.util.stream.Collectors;
import java.util.stream.IntStream;

public class Main {
    public static void main(String[] args){
        Locale locale = new Locale("en", "US");
        Locale.setDefault(locale);
        System.out.println(Thread.activeCount());//get number of active threads
        System.out.println(Runtime.getRuntime().availableProcessors());// get number of active threads
        
    }
}
```
اولی تعداد ترد هایی که استفاده میکنه رو نشون میده برای مثال داریم اینجا که 2 یکی برای کده اصله کاری هست و یکی دیگه برای کاربیج کالکتور هست که ابجکت های اضافه رو برمیداره و میندازه توی سطل آشفال
برای اینکه ترد ها رو استارت بزنیم در جاوا داریم:
برای اینکه کد رو بتونیم در یک ترد اجرا کنیم باید یک کلاس درست کنیم برای کاری که میخوایم انجام بدیم و بعد اون از Runnable ارث بری کنه و بعد ما میتونیم این کار رو اجرا کنیم 
```java
package hassandn.com;

public class DownloadFIleTask implements Runnable {

    @Override
    public void run() {
        System.out.println("Downloading File "+ Thread.currentThread().getName());
    }
}
package hassandn.com;



public class Main {
    public static void main(String[] args){
        System.out.println(Thread.currentThread().getName());
        Thread thread = new Thread(new DownloadFIleTask());
        thread.start();


    }
}
```
جاوا ی چیز داره به نام ترد اسکجوئل که برنامه ریزی میکنه که اکه تعداد کور ها کم بود هی بین ترد ها عوض کنه تا ما فکلر کنیم که ترد ها دارن جدا جدا کار انجام میدن 
#### pausing a thread
برای اینکه یک ترد رو پاز بدیم خواهیم داشت :
```java
package hassandn.com;

public class DownloadFIleTask implements Runnable {

    @Override
    public void run() {
        System.out.println("Downloading File "+ Thread.currentThread().getName());
        try {
            Thread.sleep(5000);
        } catch (InterruptedException e) {
            throw new RuntimeException(e);
        }
        System.out.println(Thread.currentThread().getName() + " Is now Unable");
    }
}
```
#### joining threads
برای اینکه ترد ها رو بهم بچسبونیم از JOIN استفاده میکنیم 
```java
package hassandn.com;



public class Main {
    public static void main(String[] args){
        System.out.println(Thread.currentThread().getName());

        Thread thread = new Thread(new DownloadFIleTask());
        thread.start();
        try {
            thread.join();
        } catch (InterruptedException e) {
            throw new RuntimeException(e);
        }
        System.out.println("its a main thread and its ended");

    }
}
```
توی این کد ترد مین صبر میکنه برای ترد دانلود وقتی کارش تموم شد مرچ میشن و به کار ادامه میده 
#### interrupting threads
اینتراپت برای مجبور کردن به قطع ترد نیست بلکه برای این هست که درخواست میکنه که اونترد متوقف بشه برای همین باید تو کدی که برای ترد مینویسیم قسمتی باشه که چک کنه که آیا ما ترد رو میگیم یا نه مثلا برای دانلود بعد از دو ثانیه میخوایم که دانلود متوقف بشه برای این باید توی کد وقتی دانلود میکنه بالاش چک کنیم که آیا اینتراپت اومده یا نه 

```java
package hassandn.com;

public class DownloadFIleTask implements Runnable {

    @Override
    public void run() {
        System.out.println("Downloading File "+ Thread.currentThread().getName());
        for (var I = 0; I < Integer.MAX_VALUE; I++){
            System.out.println("downloading "+ I);
        }
        System.out.println(Thread.currentThread().getName() + " Is now Unable");
    }
}
```
در کل ایتراپت رو مین میده ولی در اصله کار اون خوده ترده هست که مشخل میکنه باید کنکلش کنه یا نه 
```java
package hassandn.com;



public class Main {
    public static void main(String[] args){
        System.out.println(Thread.currentThread().getName());

        Thread thread = new Thread(new DownloadFIleTask());
        thread.start();
        try {
            Thread.sleep(1000);
        } catch (InterruptedException e) {
            throw new RuntimeException(e);
        }
        thread.interrupt();

    }
}
package hassandn.com;

public class DownloadFIleTask implements Runnable {

    @Override
    public void run() {
        System.out.println("Downloading File "+ Thread.currentThread().getName());
        for (var I = 0; I < Integer.MAX_VALUE; I++){
            if (Thread.currentThread().isInterrupted()) return;
            System.out.println("downloading "+ I);
        }
        System.out.println(Thread.currentThread().getName() + " Is now Unable");
    }
}
```

#### Joining threads 
فک کن که میخوای وقتی ی فایلی دانلود شد اون رو اسکن کنی برای این ما نمیتونیم از اسلیپ استفاده کنیم چون نمیدونیم چقدر طول میکشه این کار برای همین ی راه کثیفش اینکه از thread.joining() استفاده کنیم 
```java
package hassandn.com;



public class Main {
    public static void main(String[] args){
        Thread thread = new Thread(new DownloadFIleTask());
        thread.start();
        try {
            thread.join();
        } catch (InterruptedException e) {
            throw new RuntimeException(e);
        }

        System.out.println("File Ready to be scanned!");


    }
}
```
مشکل این کار اینکه ترد اصلی باید منتظر باشه تا کاره اون تموم بشه برای همین باید ی کار بهتر انجام بدیم
```java
package hassandn.com;



public class Main {
    public static void main(String[] args){
        Thread thread = new Thread(new DownloadFIleTask());
        thread.start();

        try {
            Thread.sleep(100);
            System.out.println("-----------------------------------------------------TIME OUT-----------------------------------------------------");
        } catch (InterruptedException e){
            throw new RuntimeException(e);
        }
        thread.interrupt();
        System.out.println("File Ready to be scanned!");


    }
}
package hassandn.com;

public class DownloadFIleTask implements Runnable {

    @Override
    public void run() {
        System.out.println("downloading...");
        var file = new FileToDownload(500_000);

        for (int i =0;i<file.sizeGetter();i=i+10) {
            if (Thread.currentThread().isInterrupted()) return;
            System.out.println(i);
        }

    }
}
package hassandn.com;

public class FileToDownload {
    double size;
    public  FileToDownload(double size){
        this.size =size;
    }

    public double sizeGetter(){
        return size;
    }
}

```
#### Interrupting a Thread 
وقتی ی ترد داریم که ی کاره زیادی رو انجام میده و به کاربر میخوایم بگیم که بتونه کنسل کنه 
اگه ترد اسلیپ باشه و ما بهش یگیم انتراپت کنه اکسپشن میندازه برای همین باید چکش کنیم
#### Concurrency Issues
مالتی پل ترد ها به یک آبجکت دسترسی دارن برای همین ی سری مشکلات پیش میاد هم برای دانلود و هم برا مثال اینکه یکی آبجکت رو عوض کرده ولی برای بقیه ترد ها اون عوض نشده 
اولین مشکل اینکه همشون بخوان هم زمان یک آبجکت رو تغییر بدن به صورت همزمان که بهش میگن Race Condition
دومی اینکه یک ترد دیتا رو عوض میکنه ولی تغییرات برای بقیه ترد ها قابل نمایش نیستن که بهش میگن Visibility Problem
برای اینکه به این مشکلات نخوریم باید از Thread Safe Code استفاده کنیم 
توی داکیومنتیشن جاوا این هست مثلا میگه که فلان کلاس ترد سیف هست 
#### Race Condition
توی این کد ده تا ترد داریم که به یک آبجکت همزمان متصل هستن تا اون ور تغییر بدن :
```java
package hassandn.com;


import java.util.ArrayList;
import java.util.List;

public class Main {
    public static void main(String[] args){

        var status = new DownloadStatus();

        List<Thread> threads = new ArrayList<>();
        for (int i =0;i <11 ;i++){
            var thread = new Thread(new DownloadFIleTask(status));
            thread.start();
            threads.add(thread);
        }
        for (var thread: threads){
            try {
                thread.join();
            } catch (InterruptedException e) {
                throw new RuntimeException(e);
            }
        }

        System.out.println(status.getTotalBytes());
    }
}
package hassandn.com;

public class DownloadFIleTask implements Runnable {

    private DownloadStatus status;

    public DownloadFIleTask(DownloadStatus status) {

        this.status = status;
    }

    @Override
    public void run() {
        System.out.println("downloading...");
        for (int i=0;i < 10_000;i++){
            if (Thread.currentThread().isInterrupted()) return;
            status.increamentTotalBytes();
        }


    }
}
package hassandn.com;

public class DownloadStatus {
    private int totalBytes;

    public void increamentTotalBytes(){
        totalBytes++;
    }

    public int getTotalBytes(){
        return totalBytes;
    }
}
```
اینجا هیچ وقت جواب نمیشه 10_000 چون همه ترد ها به هم وصلن و مشخص نیست کی کاره اون ترده تموم میشه به این میگن race condition
non atomic operation 
چون چند تا کار نیاز داره برای اینکریمنت کردن بهش میگن نان اتومیک 

#### strategies for thread safety
یک روش برای اینکه به این مشکل دیگه بر نخوریم 
1. confinment
یعنی اینکه از همون اول این کار رو نکنیم برای مثال به جای اینکه همه ترد ها یک آبجکت داشته باشن برای شیر کردن دیتا خواهیم دید که به مشکل میخوریم برای همین بهتره که برای هر دانلود تسک یک تکه برای استتوسش باشه
2. immutability
استفاده از آبجکت های غیر قابل تغییر مثلا آبجکت های استرینگ ایمیوتیبل هستن و تغییر نمیکنن و اگه ازشون آپر کیس درست کنیم در اصل تغییری نمیکنن
3. synchronization
جلوگیری کردن از دسترسی همزمان چند تا ترد به یک آجبکت ماز لاک استفاده میکنیم برای اینکار یعنی اینکه قفل میزنیم و فقط یک ترد میتونه با این آجبکت در زمان کار کنه
اینجا یک سری مشکلا پیش میاد اول اینکه به صورت صف طور کار میکنن اینا و ی مشکل دیگش اینکه deadlock هست که ترد یک منتظره ترده دو هست در حالیکه ترده دو منتظره ترد یک هست
و به صورت کلی باید تا جایی که میشه از سینکورانایزیشن دوری کرد
4. atomic objects
ی راه دیگه استفاده از کلاس های اتومیک هست مثل اتومیک اینتیجر ها
مثلا به جای اینکه برای اضافه کردن نیاز به سه مرحله باشه(گرفتن دیتا اضافه کردنش و بعد سیو کردنش) همش توی یک سیکل انجام میشه اینها مثل اتم هستن نمیتونن بشکنن
5. partitioning
یعنی دیتا رو بزاری توی سگمنتی که بشه همزمان به اون دیتا دسترسی داشت
جاوا کلی کلاس کانکارنس داره که میتونیم به دیتا به صورت پارتیشیونالی دسترسی داشته باشیم
#### confinment
توی کاینفاینمت میایم برای هر ترد یک آبجکت میزاریم در کد زیر داریم :
```java
package hassandn.com;


import java.util.ArrayList;
import java.util.List;

public class Main {
    public static void main(String[] args){
        List<Thread> threads = new ArrayList<>();
        List<DownloadFIleTask> tasks = new ArrayList<>();

        for (int i =0;i <11 ;i++){
            DownloadFIleTask task = new DownloadFIleTask();
            tasks.add(task);

            var thread = new Thread(task);
            thread.start();
            threads.add(thread);
        }
        for (var thread: threads){
            try {
                thread.join();
            } catch (InterruptedException e) {
                throw new RuntimeException(e);
            }
        }
        var result = tasks
                .stream()
                .map(t -> t.getStatus().getTotalBytes())
                .reduce(Integer::sum);
        System.out.println(result);
        ;
    }
}

package hassandn.com;

import java.io.File;

public class FileToDownload {
    private double size;
    public  FileToDownload(double size){
        this.size =size;
    }

    public void fileIncreament(){
        size++;
    }
    public double sizeGetter(){
        return size;
    }
}

package hassandn.com;

public class DownloadStatus {
    private int totalBytes;

    public void increamentTotalBytes(){
        totalBytes++;
    }

    public int getTotalBytes(){
        return totalBytes;
    }
}

package hassandn.com;

public class DownloadFIleTask implements Runnable {


    private DownloadStatus status;


    public DownloadFIleTask() {

        this.status = new DownloadStatus();
    }

    @Override
    public void run() {
        System.out.println("downloading...");
        for (int i=0;i < 10_000;i++){
            if (Thread.currentThread().isInterrupted()) return;
            status.increamentTotalBytes();
        }


    }
    public DownloadStatus getStatus() {
        return status;
    }
}

```
#### locks 
ی راه دیگه برای اینکه جلوگیری کنیم از مشکله race condition برای همین باید سینکرونایز کنیم برای اینکار از لاک ها استفاده میکنیم تا به جاوا ویچوال ماشین بگیم فقط یک ترد در لحظه استفاده کنه از داده که بهش میگن critical section
برای این تنها کاری که لازمه انجام بدیم اینکه یک آبجکت از لاک بسازیم و از این اینطوری برای آبجکتی که در خطره استفاده کنیم 
```java
package hassandn.com;

import java.util.concurrent.locks.Lock;
import java.util.concurrent.locks.ReentrantLock;

public class DownloadFIleTask implements Runnable {


    private DownloadStatus status;
    private Lock lock = new ReentrantLock();


    public DownloadFIleTask() {

        this.status = new DownloadStatus();
    }

    @Override
    public void run() {
        System.out.println("downloading...");
        for (int i=0;i < 10_000;i++){
            if (Thread.currentThread().isInterrupted()) return;
            status.increamentTotalBytes();
        }


    }
    public DownloadStatus getStatus() {
        lock.lock();
        try {
            return status;
        }finally {
            lock.unlock();
        }
    }
}
```

باید اون کارمون رو بزاریم توی ترای کچ تا اگه خطا داد دچار خطای دد لاک نشیم 
#### the synchronized keyword 
