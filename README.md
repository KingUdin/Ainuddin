# Ainuddin
// Java Program to Display Current Date and Time
import java.util.*;
  
public class GFG {
    public static void main(String args[])
    {
        Date current_Date = new Date();
        //"Date" class
        //"current_Date" is Date object
  
        System.out.println(current_Date);
        // print the time and date
    }
}




Conversion of GMT form to IST using two classes called TimeZone, it also comes under util package of Java, and SimpleDateFormat


// Java Program to Display Current Date and Time
import java.text.*;
import java.util.*;
public class GFG {
    public static void main(String args[])
    {
        SimpleDateFormat formatDate = new SimpleDateFormat(
            "dd/MM/yyyy  HH:mm:ss z");
        //"SimpleDateForma" class initialize with object
        //"formatDate" this class acceptes the format of
        // date and time as ""dd/MM/yyyy" and "HH:mm:ss z""
        //"z" use for print the time zone
  
        Date date = new Date();
        // initialize "Date" class
  
        formatDate.setTimeZone(TimeZone.getTimeZone("IST"));
        // converting to IST or fornmat the Date as IST
  
        System.out.println(formatDate.format(date));
        // print formatted date and time
    }
}


LocalDateTime class which can also represent the current date and time in GMT form. We can get the IST form by adding 5 hours and 30 minutes to the GMT form.


// Java Program to Display Current Date and Time
import java.time.*;
public class MyClass {
    public static void main(String args[])
    {
        System.out.println(LocalDateTime.now());
        //"LocalDateTime" is the class
        //"now()" is a method, represent the
        // current date and time
    }
}




convert this GMT form to IST using a class called ZonedDateTime

// Java Program to Display Current Date and Time
import java.util.*;
import java.time.*;
public class GFG {
    public static void main(String[] args)
    {
        Date date = new Date();
  
        LocalDateTime d = LocalDateTime.now();
  
        ZonedDateTime UTCtime = d.atZone(ZoneId.of("UTC"));
        //"d" is the current date and
        //"ZonedDateTime" accepts "d" as UTC
        //"atZone" specifies the time zone
  
        // converting to IST
        ZonedDateTime ISTtime = UTCtime.withZoneSameInstant(
            ZoneId.of("Asia/Kolkata"));
        //"withZoneSameInstant" convert the time
        // to given time zone
  
        System.out.println(ISTtime);
        // print the time and date
    }
}





