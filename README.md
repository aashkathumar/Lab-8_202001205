# Lab-8_202001205

### **IT314-Software Engineering Lab-8**

### **Unit Testing with JUnit**

### **Name: - Aashka Arvindbhai Thumar**

### **Student ID: - 202001205**


### **Aim: -** To learn how to use JUnit to write unit tests for Java programs in Eclipse software.

**The Boa Class File:**

Created and added a method of the name **"lengthInInches()"** to return the length in inches to the existing code.

**Code:** 
    
    package lab8_202001205;

    public class Boa {
        private String name;
        private int length; // the length of the boa, in feet
        private String favoriteFood;
        public Boa (String name, int length, String favoriteFood)
        {
            this.name = name;
            this.length = length;
            this.favoriteFood = favoriteFood;
        }
        // returns true if this boa constructor is healthy
        public boolean isHealthy()
        {
            return this.favoriteFood.equals("granola bars");
        }
        // returns true if the length of this boa constructor is
        // less than the given cage length
        public boolean fitsInCage(int cageLength)
        {
            return this.length < cageLength;
        }
        public int lengthInInches()
        {
            return this.length*12;
        }
    }

![1](https://user-images.githubusercontent.com/75677392/233311409-102b9e04-d36d-4bbd-bb67-c46638c9ede9.jpg)

**Creating testcases in the BoaTest file:**

This part of the code shall run before any testcase is made to run. Two objects are created with different parameters. The setUp function is then modified with the first object jen with the name Jennifer, length 2 and favourite food beind grapes. The second object ken with the name Kenneth, lenth 3 and favourite food granola bars.

**Code:**

    package lab8_202001205;

    import static org.junit.Assert.*;

    import org.junit.Test;

    public class Boa_test {

        private Boa jen;
        private Boa ken;

        @Before
        public void setUp() throws Exception {
            jen = new Boa("Jennifer", 2, "grapes");
            ken = new Boa ("Kenneth", 3, "granola bars");
      }

![1_1](https://user-images.githubusercontent.com/75677392/233316599-0aa2ab52-58df-4b2f-a191-59158bca4c35.png)

**1. Testcases for isHealthy function:**

Returns true for ken as it's favourite food is given as granola bars in th eparameter as set in th emain java class file.

**Code:**

    @Test
    public void testIsHealthy_1()
    {
        boolean output = ken.isHealthy();
        assertEquals(output,true);
    }

    @Test
    public void testIsHealthy_2()
    {
        boolean output = jen.isHealthy();
        assertEquals(output,false);
    }

![1_2](https://user-images.githubusercontent.com/75677392/233316825-d577e5f1-3c80-4468-888a-7b17188add0a.png)

**2. Testcases for fitsInCage function:**

Returns true if the size of the cage is greater than th elength of the object.

**Code:**

    @Test
    public void testFitsInCage_1()
    {
        int cage = 2;
        boolean output = jen.fitsInCage(cage);
        assertEquals(output,false);
    }

    @Test
    public void testFitsInCage_2()
    {
        int cage = 1;
        boolean output = ken.fitsInCage(cage);
        assertEquals(output,false);
    }

    @Test
    public void testFitsInCage_3()
    {
        int cage = 10;
        boolean output = ken.fitsInCage(cage);
        assertEquals(output,true);
    }

    @Test
    public void testFitsInCage_4()
    {
        int cage = 3;
        boolean output = ken.fitsInCage(cage);
        assertEquals(output,false);
    }

![3](https://user-images.githubusercontent.com/75677392/233311514-55c78d29-239b-4292-b384-a463c013289c.jpg)

**3. Testcases for LengthInInches function:**

Returns the length converted into inches on application of the forula in the method created.

**Code:**

      @Test
      public void lengthInInches_1()
      {
          int output = jen.lengthInInches();
          assertEquals(output,24);
      }

      @Test
      public void lengthInInches_2()
      {
          int output = ken.lengthInInches();
          assertEquals(output,36);
      }

    }

![4](https://user-images.githubusercontent.com/75677392/233311536-0a4240ed-3ae9-4860-b791-7bf1eb46563f.jpg)
