宏`panic!`用于在当前线程制造一个运行时错误（俗称叛逆）并开始栈回溯(stack unwinding)。
在回溯过程中，运行时(runtime)将负责调用析构函数，释放当前栈所拥有的(owned)所有对象的所有资源。

因为我们这个程序只有一个线程，`panic!`将导致该程序输出叛逆信息后结束运行。

{panic.play}

请看，`panic!`不会导致内存泄露。

```
$ rustc panic.rs && valgrind ./panic
==4401== Memcheck, a memory error detector
==4401== Copyright (C) 2002-2013, and GNU GPL'd, by Julian Seward et al.
==4401== Using Valgrind-3.10.0.SVN and LibVEX; rerun with -h for copyright info
==4401== Command: ./panic
==4401== 
task '<main>' panicked at 'division by zero', panic.rs:5
==4401== 
==4401== HEAP SUMMARY:
==4401==     in use at exit: 0 bytes in 0 blocks
==4401==   total heap usage: 18 allocs, 18 frees, 1,648 bytes allocated
==4401== 
==4401== All heap blocks were freed -- no leaks are possible
==4401== 
==4401== For counts of detected and suppressed errors, rerun with: -v
==4401== ERROR SUMMARY: 0 errors from 0 contexts (suppressed: 0 from 0)
```
