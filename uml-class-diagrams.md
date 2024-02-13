     UML Class Diagrams

UML Class Diagrams
==================

**ClassName**

_vis_ _attribute_ : _type_

_vis_ _operation_(_arg list_) : _return type_

where

*   _vis_ = visibility (+ for public, \- for private)
*   _attribute_ = data member (aka field)
*   _operation_ = method (or constructor)

Note:

*   The _arg list_ is a list of parameter types (e.g., int, double, String); parameter names are _not_ included in the UML class diagram
*   Methods that don't return a value (i.e. void methods) should give a _return type_ of void
*   Class (i.e. static) methods and fields are indicated by underlining
*   Constant (i.e. final) fields are indicated via naming convention: constants should be in ALL\_CAPS

Example:
========

UML diagram
-----------

**Employee**

\-name:String  
\-payRate:double  
\-EMPLOYEE\_ID:int  
\-nextID:int  
+STARTING\_PAY\_RATE:double

+Employee(String)  
+Employee(String, double)  
+getName():String  
+getEmployeeID():int  
+getPayRate():double  
+changeName(String):void  
+changePayRate(double):void  
+getNextID():int

Corresponding Java Class
------------------------

public class Employee {

    private String name;
    private double payRate;
    private final int EMPLOYEE\_ID;
    
    private static int nextID = 1000;
    
    public static final double STARTING\_PAY\_RATE = 7.75;
    
    public Employee(String name) {
        this.name = name;
        EMPLOYEE\_ID = getNextID();
        payRate = STARTING\_PAY\_RATE;
    }
    
    public Employee(String name, double startingPay) {
        this.name = name;
        EMPLOYEE\_ID = getNextID();
        payRate = startingPay;
    }
    
    public String getName() { return name; }
    
    public int getEmployeeID() { return EMPLOYEE\_ID; }
    
    public double getPayRate() { return payRate; }
    
    public void changeName(String newName) { name = newName; }
    
    public void changePayRate(double newRate) { payRate = newRate; }
    
    public static int getNextID() {
        int id = nextID;
        nextID++;
        return id;
    }
}
