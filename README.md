import sympy as sp

x = sp.symbols('x')
f = sp.sympify(input("أدخل الدالة f(x): "))
df = sp.diff(f, x)

x0 = float(input("قيمة البداية x0: "))
tol = float(input("أدخل نسبة السماحية (Tolerance مثل 1e-6): "))

max_iter = 1000  # حد أقصى للتكرارات لمنع الدوران اللانهائي
i = 0

while i < max_iter:
    fx = float(f.subs(x, x0))
    dfx = float(df.subs(x, x0))
    
    if dfx == 0:
        print("خطأ: المشتقة تساوي صفراً!")
        break
        
    x_next = x0 - fx / dfx
    i += 1
    
    print(f"التكرار {i}: {x_next}")
    
    # شرط التوقف: إذا كان الفرق أصغر من السماحية المطلوبة
    if abs(x_next - x0) < tol:
        print("\nتم الوصول للتقارب المطلوب!")
        x0 = x_next
        break
        
    x0 = x_next

print(f"الجذر التقريبي النهائي هو: {x0}")
