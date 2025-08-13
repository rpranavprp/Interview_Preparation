# Day 1 – C# Advanced Concepts: Q&A

1. **Q: What’s the difference between Task and Thread in C#?**  
   **A:**  
   Think of a `Thread` like a worker in a factory — you tell them to start, and they do one job until it’s finished.  
   A `Task` is like a project manager that decides which worker should handle the job, and may even use multiple workers internally.  

   In modern C#, we mostly use `Task` with `async/await` because it’s easier to handle, more scalable, and works better with the thread pool.  

   **Real Project Example:**  
   In our payment gateway integration project, instead of creating a new thread for every bank verification request, we used:  

   ```csharp
   await VerifyBankDetailsAsync();
