# JuliaSharp

C#与Julia交互

C# Interop for Julia

## 使用方法 Usage

引用 Using
```C#
using JuliaSharp;
```

简单类型和数组 Primitives and Array
```C#
JuliaNative.InitThreading();
JuliaNative.EvalString("println(123)");

JuliaValue<double> r = JuliaNative.EvalString("sqrt(2.0)");
double d = r;
Console.WriteLine($"{d}");

JuliaValue<long> s2 = 2;
long s3 = s2;
Console.WriteLine($"{s3}");

var da = JuliaArray<double>.Create1D(10);
Console.WriteLine(da);

JuliaArray<double> db = JuliaNative.EvalString("rand(1,3)");
Console.WriteLine(db);

JuliaArray<double> dc = JuliaNative.EvalString("rand(10,4)");
Console.WriteLine(dc);

JuliaArray<double> dd = JuliaNative.EvalString("rand(3,1)");
Console.WriteLine(dd);

JuliaArray<long> de = JuliaNative.EvalString("ones(Int64, 2, 2)");
Console.WriteLine(de);

JuliaNative.AtExitHook(0);
```
