# UML Class Diagrams


## Rule of Thumb

1) Give class name,
2) Show the visibility of fields,
3) Show the visibility of operation( or constructor)

4) The arg list is a list of parameter types (e.g., int, double, String).
5) Parameter names are not included in the UML class diagram.
6) Methods that don't return a value (i.e. void methods) should give a return type of void.

7) Class (i.e. static) methods and fields are indicated by underlining.
8) Constant (i.e. final) fields are indicated via naming convention: constants should be in ALL_CAPS.


|ClassName                     | 
|------------------------------|
visibility attribute : type
visibility operation(arg list) : return type

 


## Example:


Example of a Java Class

public class Employee {

    private String name;
    private double payRate;
    private final int EMPLOYEE_ID;
    
    private static int nextID = 1000;
    
    public static final double STARTING_PAY_RATE = 7.75;
    
    public Employee(String name) {
        this.name = name;
        EMPLOYEE_ID = getNextID();
        payRate = STARTING_PAY_RATE;
    }
    
    public Employee(String name, double startingPay) {
        this.name = name;
        EMPLOYEE_ID = getNextID();
        payRate = startingPay;
    }
    
    public String getName() { return name; }
    
    public int getEmployeeID() { return EMPLOYEE_ID; }
    
    public double getPayRate() { return payRate; }
    
    public void changeName(String newName) { name = newName; }
    
    public void changePayRate(double newRate) { payRate = newRate; }
    
    public static int getNextID() {
        int id = nextID;
        nextID++;
        return id;
    }
}



## UML diagram of the above Employee class


|Employee                     |
|-----------------------------|
 -name:String
 -payRate:double
 -EMPLOYEE_ID:int
 -nextID:int
<u>+STARTING_PAY_RATE:double<u>
|---------------------------- |
 <u>+Employee(String)<u>
 <u>+Employee(String, double)<u>
 +getName():String
 +getEmployeeID():int
 +getPayRate():double
 +changeName(String):void
 +changePayRate(double):void
 <u>+getNextID():int<u>


