[stack overflow](https://stackoverflow.com/questions/9777822/what-does-to-stub-mean-in-programming)

1) A stub is a controllable replacement for an Existing depedency in the system
A stub is a controllable replacement for an **Existing Dependency** (or collaborator) in the system. By using a stub, you can test your code without dealing with the dependency directly.

**External Dependency - Existing Dependency:**  
It is an object in your system that your code under test interacts with and over which you have no control. (Common examples are filesystems, threads, memory, time, and so on.)

Forexample in below code:
```cs
public void Analyze(string filename)
    {
        if(filename.Length>8)
        {
            try
            {
                errorService.LogError("long file entered named:" + filename);
            }
            catch (Exception e)
            {
                mailService.SendEMail("admin@hotmail.com", "ErrorOnWebService", "someerror");
            }
        }
    }
```
You want to test **mailService.SendEMail()** method, but to do that you need to simulate an _Exception_ in your test method, so you just need to create a Fake Stub **errorService** object to simulate the result you want, then your test code will be able to test **mailService.SendEMail()** method. As you see you need to simulate a result which is from an another Dependency which is **ErrorService** class object (Existing Dependency object).

2) In layman terms
In laymen terms: Anything that the code uses. It might help to understand if you re-read and replace "dependency" with "class" or "function" or whatever (depends on your background). Sometimes using the existing class/function isn't a viable option and you need a stub (e.g. in automated unit-testing for functions that rely on the environment such as the system's current date & time)

3) A stub, in this context, means a mocking implementation
A [stub](http://en.wikipedia.org/wiki/Method_stub), in this context, means a mock implementation.
That is, a simple, fake implementation that conforms to the interface and is to be used for testing

4) Layman's terms, it's dummy data
Layman's terms, it's dummy data (or fake data, test data...etc.) that you can use to test or develop your code against until you (or the other party) is ready to present/receive real data. It's a programmer's "Lorem Ipsum".

Employee database not ready? Make up a simple one with Jane Doe, John Doe...etc. API not ready? Make up a fake one by creating a static .json file containing fake data.