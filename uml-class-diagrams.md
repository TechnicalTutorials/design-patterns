# UML Class Diagrams

| ClassName |

|Name|Email|Address| 
|----|-----|-------|
vis attribute : type
vis operation(arg list) : return type

### where
vis = visibility (+ for public, - for private)
attribute = data member (aka field)
operation = method (or constructor)
Note:

The arg list is a list of parameter types (e.g., int, double, String); parameter names are not included in the UML class diagram
Methods that don't return a value (i.e. void methods) should give a return type of void
Class (i.e. static) methods and fields are indicated by underlining
Constant (i.e. final) fields are indicated via naming convention: constants should be in ALL_CAPS
 

Example:
UML diagram
Employee
-name:String
-payRate:double
-EMPLOYEE_ID:int
-nextID:int
+STARTING_PAY_RATE:double
+Employee(String)
+Employee(String, double)
+getName():String
+getEmployeeID():int
+getPayRate():double
+changeName(String):void
+changePayRate(double):void
+getNextID():int
Corresponding Java Class
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
