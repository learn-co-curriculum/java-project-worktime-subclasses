# Project Work Time - Subclasses

## Learning Goals

- Spend some time working on your project.

## Introduction

You can now work on Task 3 in the Module Project. Task 3 has been copied here
for your convenience.

## Task 3 - Create the Ticket Subclasses

In the overview, you saw there will be three subclasses of the `Ticket` abstract
class. In this task, you will create those three subclasses now. Consider the
following UML diagram:

![ticket-uml](https://curriculum-content.s3.amazonaws.com/java-mod-3/project/uml-ticket-hierarchy.png)

1. Create a `WalkupTicket` class that extends the `Ticket` class.
    1. Return 50.0 for the price since walk-up tickets are purchased the day of
       the concert and cost $50.
    2. In the test directory, create a package called `ticket` under
       `src/test/java`.
    3. Within the `ticket` package in the `test` directory, add the following
       test class:

    ```java
    package ticket;
    
    import org.junit.jupiter.api.Test;
    
    import static org.junit.jupiter.api.Assertions.assertEquals;
    
    public class WalkupTicketTest {
    
        @Test
        void testWalkupTicket() {
            WalkupTicket ticket = new WalkupTicket(1);
            assertEquals(1, ticket.getTicketNumber());
            assertEquals(50.0, ticket.getPrice());
            assertEquals("ticket.Ticket Number = 1, Price = 50.00", ticket.toString());
        }
    }
    ```

    4. Run the JUnit and ensure it passes with your implementation.
2. Create a `StudentTicket` class that extends the `WalkupTicket` class.
    1. Return half the price of a walk-up ticket for the price.
    2. Within the `ticket` package in the `test` directory, add the following
       test class:

    ```java
    package ticket;
    
    import org.junit.jupiter.api.Test;
    
    import static org.junit.jupiter.api.Assertions.assertEquals;
    
    public class StudentTicketTest {
    
        @Test
        void testStudentTicket() {
            StudentTicket ticket = new StudentTicket(1);
            assertEquals(1, ticket.getTicketNumber());
            assertEquals(25.0, ticket.getPrice());
            assertEquals("ticket.Ticket Number = 1, Price = 25.00", ticket.toString());
        }
    }
    ```

    3. Run the JUnit and ensure it passes with your implementation.
3. Create an `AdvanceTicket` class that extends the `Ticket` class.
    1. Add an `int` instance variable called `daysBeforeConcert` since you can
       buy this kind of ticket in advance.
    2. In the constructor, also take in a `daysBeforeConcert` parameter that
       initializes the instance variable.
    3. Use IntelliJ to generate a getter method for the instance variable.
    4. Remember the ticket rules above when pricing out the advance ticket:
        1. If the advance ticket is purchased 10 or more days before the concert,
           then the ticket costs $30.00.
        2. Else, the ticket costs $40.00.
    5. Within the `ticket` package in the `test` directory, add the following
       test class:

    ```java
    package ticket;
    
    import org.junit.jupiter.api.Test;
    
    import static org.junit.jupiter.api.Assertions.assertEquals;
    
    public class AdvanceTicketTest {
    
        @Test
        void testAdvanceTicket10Days() {
            AdvanceTicket ticket = new AdvanceTicket(1, 10);
            assertEquals(1, ticket.getTicketNumber());
            assertEquals(10, ticket.getDaysBeforeConcert());
            assertEquals(30.0, ticket.getPrice());
            assertEquals("ticket.Ticket Number = 1, Price = 30.00", ticket.toString());
        }
    
        @Test
        void testAdvanceTicketMoreThan10Days() {
            AdvanceTicket ticket = new AdvanceTicket(2, 12);
            assertEquals(2, ticket.getTicketNumber());
            assertEquals(12, ticket.getDaysBeforeConcert());
            assertEquals(30.0, ticket.getPrice());
        }
    
        @Test
        void testAdvanceTicketLessThan10Days() {
            AdvanceTicket ticket = new AdvanceTicket(3, 9);
            assertEquals(3, ticket.getTicketNumber());
            assertEquals(9, ticket.getDaysBeforeConcert());
            assertEquals(40.0, ticket.getPrice());
        }
    }
    ```

    6. Run the JUnits and ensure it passes with your implementation.

This task can be completed after the More on Inheritance section. Note: There
will be a lesson called "Project Work Time - Subclasses" that will signal when
to start this part of the project.
