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