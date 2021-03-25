# 完成底下程式閱讀題
```
解答與說明
好好學 Java : 從零基礎到項目實戰
歐陽燊  清華大學  2020-07-01
ISBN:7302554188
ISBN-13:9787302554189
https://www.tenlong.com.tw/products/9787302554189
```

# 第二章 數學
```
//2.1
package com.arithmetic.math;


public class Angle {
	public static void main(String[] args) {
		double angle = 60;				
                double radian = angle * Math.PI / 180;
		double sin = Math.sin(radian); 	
		
                System.out.println("sin=" + sin);
		
		double cos = Math.cos(radian); 	
		System.out.println("cos=" + cos);
		
		double tan = Math.tan(radian); 	
		System.out.println("tan=" + tan);
		
		double ctan = 1.0 / tan;
		System.out.println("ctan=" + ctan);
	}

}
```

```
//2.2
package com.arithmetic.math;

import java.util.Random;


public class Rand {

	public static void main(String[] args) {
		double decimal = Math.random(); 
		System.out.println("decimal=" + decimal);
		int integer = new Random().nextInt(); 
		System.out.println("integer=" + integer);
		long long_integer = new Random().nextLong(); 
		System.out.println("long_integer=" + long_integer);
		float float_decimal = new Random().nextFloat(); 
		System.out.println("float_decimal=" + float_decimal);
		double double_decimal = new Random().nextDouble();
		System.out.println("double_decimal=" + double_decimal);
		int hundred = new Random().nextInt(100); 
		System.out.println("hundred=" + hundred);
	}

}


```
```
//2.3
package com.arithmetic.math;


public class Science {

	public static void main(String[] args) {
		double nine = 9;
		double sqrt = Math.sqrt(nine);
		System.out.println("sqrt=" + sqrt);
		double pow = Math.pow(nine, 2);
		System.out.println("pow=" + pow);
		
		double five = 5;
		double exp = Math.exp(five);
		System.out.println("exp=" + exp);
		double log = Math.log(exp);
		System.out.println("log=" + log);
		double log10 = Math.log10(100); 		
System.out.println("log10=" + log10);
	}

}


```
```
//2.4
package com.arithmetic.math;


public class Trunc {

	public static void main(String[] args) {
		double decimalPositive = 9.9;
		long roundPositive = Math.round(decimalPositive);
 	           System.out.println("roundPositive=" + roundPositive);
		double floorPositive = Math.floor(decimalPositive);		
System.out.println("floorPositive=" + floorPositive);
		double ceilPositive = Math.ceil(decimalPositive); 		
System.out.println("ceilPositive=" + ceilPositive);

		double decimalNegative = -9.9;
		long roundNegative = Math.round(decimalNegative);
		System.out.println("roundNegative=" + roundNegative);
double floorNegative = Math.floor(decimalNegative); 		   
                       System.out.println("floorNegative=" + floorNegative);
		double ceilNegative = Math.ceil(decimalNegative); 
		System.out.println("ceilNegative=" + ceilNegative);

		double absoluteValue = Math.abs(decimalNegative); 
		System.out.println("absoluteValue=" + absoluteValue);
	}

}


```
```
//2.6
package com.arithmetic.numerical;


public class Basic {

	public static void main(String[] args) {
		int zhumulanma; 
		zhumulanma = 8844; 
		System.out.println("珠穆朗玛峰的高度=" + zhumulanma);
		double yuanzhoulv = 3.1415926; 
		System.out.println("圆周率=" + yuanzhoulv);
	}
}


```
```
//2.7
package com.arithmetic.numerical;


public class Convert {

	public static void main(String[] args) {
		int changjiang = 6397; 
		System.out.println("changjiang=" + changjiang);
		int longRiver = changjiang; 
		System.out.println("longRiver=" + longRiver);
long changjiang = 6397;
int longRiver = (int) changjiang; 
		long worldPopulation = 7444443881L; 
		System.out.println("worldPopulation=" + worldPopulation);
		int shijierenkou = (int) worldPopulation; 		
System.out.println("shijierenkou=" + shijierenkou);
		
double zulv = 3.1415926;
		System.out.println("zulv=" + zulv);
		float pai = (float) zulv; 		
System.out.println("pai=" + pai);
		double jiage = 9.9;		
System.out.println("jiage=" + jiage);
		int price = (int) jiage; 
		System.out.println("price=" + price);
	}
}


```
```
//2.8
package com.arithmetic.numerical;


public class Prefix {

	public static void main(String[] args) {
		int binary = 0b11; 
		System.out.println("binary=" + binary);
		int octonary = 011; 
		System.out.println("octonary=" + octonary);
		int hexadecimal = 0x11; 
		System.out.println("hexadecimal=" + hexadecimal);
		int hexLetter = 0xff; 
		System.out.println("hexadecimal=" + hexLetter);
		int decimal = 11; 
		System.out.println("decimal=" + decimal);
	}
}


```
```
//2.9
package com.arithmetic.numerical;


public class Suffix {

	public static void main(String[] args) {
		
		
		long worldPopulation = 7444443881L; 
		System.out.println("worldPopulation=" + worldPopulation);
		float huilv = 3.14F; 
		System.out.println("huilv=" + huilv);
		int chinaArea = 960_0000; 
		System.out.println("chinaArea=" + chinaArea);
		double sunDistance = 1.5E8; 
		System.out.println("sunDistance=" + sunDistance);
	}
}


```
```
//2.11
package com.arithmetic.operator;


public class Assign {

	public static void main(String[] args) {
		
		int x = 1 + 1;
		System.out.println("初始值 x=" + x);
		
		
		
		x += 7; 
		System.out.println("相加之和 x=" + x);
		
		x -= 7;
		System.out.println("相减之差 x=" + x);
		
		x *= 7; 
		System.out.println("相乘之积 x=" + x);
		
		x /= 7; 
		System.out.println("相除之商 x=" + x);
		
		x %= 7; 
		System.out.println("相除之余 x=" + x);
		
		x <<= 2; 
		System.out.println("x按位左移两位=" + x);
		
		x >>= 2; 
		System.out.println("x按位右移两位=" + x);
	}
}


```
```
//2.12
package com.arithmetic.operator;


public class Four {

	public static void main(String[] args) {
		int sum = 1 + 2; 
		System.out.println("sum=" + sum);
		int differ = 7 - 3; 
		System.out.println("differ=" + differ);
		int product = 5 * 6; 
		System.out.println("product=" + product);
		int quotient = 81 / 9; 
		System.out.println("quotient=" + quotient);
		int remainder = 40 % 3;
		System.out.println("remainder=" + remainder);
		
		int quotientInt = 25 / 4;
		System.out.println("quotientInt=" + quotientInt);
		
		double quotientDouble = 25.0 / 4; 
		System.out.println("quotientDouble=" + quotientDouble);
		
		double quotientDecimal = 8.1 / 3;
		System.out.println("quotientDecimal=" + quotientDecimal);
		
		double remainderDecimal = 5.1 % 2;
		System.out.println("remainderDecimal=" + remainderDecimal);
	}
}


```
```
//2.13
package com.arithmetic.operator;


public class Unary {

	public static void main(String[] args) {
		int x = 3;
		System.out.println("初始 x=" + x);
		x++; 
		System.out.println("自增1 x=" + x);
		x--; 
		System.out.println("自减1 x=" + x);
		
		x *= x; 
		System.out.println("求平方 x=" + x);
		
		double y = 1.0 / x; 
		System.out.println("求倒数 y=" + y);
		x = -x; 
		System.out.println("负数 x=" + x);
		x = +x; 
		System.out.println("正数 x=" + x);
		int y1 = 7;
		int z1 = y1++; 
		
		System.out.println("z1=" + z1);
		int y2 = 7;
		int z2 = ++y2; 
		
		System.out.println("z2=" + z2);
		
		int z3 = ++z1 + z2++;
		System.out.println("z3=" + z3);
	}
}


```
```
//2.14
package com.arithmetic;


public class Niudundiedai {

	public static void main(String[] arg) {
		double number = 7; 
		int n = 3; 
		double Xm = number; 
		double slope; 
		
		slope = n * Math.pow(Xm, n-1); 
		Xm = Xm - (Math.pow(Xm, n)-number)/slope; 
		System.out.println(number+"的"+n+"次方根="+Xm);

		slope = n * Math.pow(Xm, n-1); 
		Xm = Xm - (Math.pow(Xm, n)-number)/slope; 
		System.out.println(number+"的"+n+"次方根="+Xm);

		slope = n * Math.pow(Xm, n-1); 
		Xm = Xm - (Math.pow(Xm, n)-number)/slope;
		System.out.println(number+"的"+n+"次方根="+Xm);

		slope = n * Math.pow(Xm, n-1); 
		Xm = Xm - (Math.pow(Xm, n)-number)/slope; 
		System.out.println(number+"的"+n+"次方根="+Xm);

		slope = n * Math.pow(Xm, n-1); 
		Xm = Xm - (Math.pow(Xm, n)-number)/slope; 
		System.out.println(number+"的"+n+"次方根="+Xm);
	}
}


```
```
//2.15
package com.arithmetic;


public class Pingfanggen {

	public static void main(String[] arg) {

		double number = 3; 
		double Xm = number; 
		
		Xm = (Xm + number/Xm) / 2; 
		System.out.println(number+"的平方根="+Xm);

		Xm = (Xm + number/Xm) / 2; 
		System.out.println(number+"的平方根="+Xm);

		Xm = (Xm + number/Xm) / 2; 
		System.out.println(number+"的平方根="+Xm);
	}
}


```
```
//2.16
package com.arithmetic;


public class Yuanzhoulv {
	
	public static void main(String[] arg) {
		
		int r = 1; 
		long edgeNumber = 6L; 
		double edgeLength = r; 
		double π = edgeLength * edgeNumber / (2*r); 
		System.out.println("正n边形的边数="+edgeNumber+"，圆周率="+π);
		double gou;
		double gu; 

		
		edgeNumber = edgeNumber*2; 
		gou = edgeLength/2.0; 
		gu = r - Math.sqrt(Math.pow(r,2) - Math.pow(gou,2)); 
		edgeLength = Math.sqrt(Math.pow(gou,2) + Math.pow(gu,2));
		
		π = edgeLength * edgeNumber / (2*r);
		System.out.println("正n边形的边数="+edgeNumber+"，圆周率="+π);

		
		edgeNumber = edgeNumber*2;
		gou = edgeLength/2.0; 
		gu = r - Math.sqrt(Math.pow(r,2) - Math.pow(gou,2)); 
		edgeLength = Math.sqrt(Math.pow(gou,2) + Math.pow(gu,2));
		
		π = edgeLength * edgeNumber / (2*r);
		System.out.println("正n边形的边数="+edgeNumber+"，圆周率="+π);

		
		edgeNumber = edgeNumber*2;
		gou = edgeLength/2.0; 
		gu = r - Math.sqrt(Math.pow(r,2) - Math.pow(gou,2)); 
		
		edgeLength = Math.sqrt(Math.pow(gou,2) + Math.pow(gu,2));
		
		π = edgeLength * edgeNumber / (2*r);
		System.out.println("正n边形的边数="+edgeNumber+"，圆周率="+π);

		
		edgeNumber = edgeNumber*2; 
		gou = edgeLength/2.0; 
		gu = r - Math.sqrt(Math.pow(r,2) - Math.pow(gou,2)); 
		edgeLength = Math.sqrt(Math.pow(gou,2) + Math.pow(gu,2));
		
		π = edgeLength * edgeNumber / (2*r);
		System.out.println("正n边形的边数="+edgeNumber+"，圆周率="+π);

		
		edgeNumber = edgeNumber*2; 
		gou = edgeLength/2.0; 
		gu = r - Math.sqrt(Math.pow(r,2) - Math.pow(gou,2)); 
		edgeLength = Math.sqrt(Math.pow(gou,2) + Math.pow(gu,2));
		
		π = edgeLength * edgeNumber / (2*r);
		System.out.println("正n边形的边数="+edgeNumber+"，圆周率="+π);

		
		edgeNumber = edgeNumber*2; 
		gou = edgeLength/2.0; 
		gu = r - Math.sqrt(Math.pow(r,2) - Math.pow(gou,2)); 
		edgeLength = Math.sqrt(Math.pow(gou,2) + Math.pow(gu,2));
		
		π = edgeLength * edgeNumber / (2*r);
		System.out.println("正n边形的边数="+edgeNumber+"，圆周率="+π);

		
		edgeNumber = edgeNumber*2; 
		gou = edgeLength/2.0; 
		gu = r - Math.sqrt(Math.pow(r,2) - Math.pow(gou,2)); 
		edgeLength = Math.sqrt(Math.pow(gou,2) + Math.pow(gu,2));
		
		π = edgeLength * edgeNumber / (2*r);
		System.out.println("正n边形的边数="+edgeNumber+"，圆周率="+π);

		
		edgeNumber = edgeNumber*2; 
		gou = edgeLength/2.0; 
		gu = r - Math.sqrt(Math.pow(r,2) - Math.pow(gou,2)); 
		edgeLength = Math.sqrt(Math.pow(gou,2) + Math.pow(gu,2));
		
		π = edgeLength * edgeNumber / (2*r);
		System.out.println("正n边形的边数="+edgeNumber+"，圆周率="+π);

		
		edgeNumber = edgeNumber*2; 
		gou = edgeLength/2.0; 
		gu = r - Math.sqrt(Math.pow(r,2) - Math.pow(gou,2)); 
		
		edgeLength = Math.sqrt(Math.pow(gou,2) + Math.pow(gu,2));
		
		π = edgeLength * edgeNumber / (2*r);
		System.out.println("正n边形的边数="+edgeNumber+"，圆周率="+π);

	}

}


```

# 第3章邏輯控制
```
//3.1
package com.control.array;

import java.util.Arrays;


public class ArrayCopy {

	public static void main(String[] args) {
		int[] pricesOrigin = { 99, 99, 99, 99, 99 }; 

		int[] pricesAssign = pricesOrigin;
		pricesOrigin[1] = 80;
		for (int price : pricesAssign) { 
			System.out.println("assign price = " + price);
		}

		/
		int[] pricesPart = Arrays.copyOf(pricesOrigin, pricesOrigin.length - 1);
		for (int price : pricesPart) { 
			System.out.println("part price = " + price);
		}

		
		pricesOrigin = Arrays.copyOf(pricesOrigin, pricesOrigin.length + 1);
		for (int price : pricesOrigin) { 
			System.out.println("origin price = " + price);
		}
	}
}


```

```
//3.2
package com.control.array;

import java.util.Arrays;


public class ArrayFill {

	public static void main(String[] args) {
		
		int[] prices = new int[10]; 
		Arrays.fill(prices, 99);
		for (int price : prices) { 
			System.out.println("price = "+price);
		}
	}
}


```
```
//3.3
package com.control.array;

import java.util.Arrays;
import java.util.Random;


public class ArraySort {

	public static void main(String[] args) {
		int[] prices = { 99, 80, 18, 68, 8 };
		
		Arrays.sort(prices);
		for (int price : prices) { 
			System.out.println("price = " + price);
		}

		int[] numbers = new int[10]; 
		loop: for (int i = 0; i < numbers.length; i++) {
			int item = new Random().nextInt(100); 
			
			for (int j = 0; j < i; j++) {
				if (numbers[j] == item) { 
					i--; 
					continue loop; 
				}
			}
			numbers[i] = item; 
		}
		
		Arrays.sort(numbers);
		for (int number : numbers) { 
			System.out.println("number = " + number);
		}
	}
}


```
```
//3.4
package com.control.array;


public class ColonErgodic {

	public static void main(String[] args) {
		int[] numbers = { 2, 3, 5, 7 };

		for (int number : numbers) {
			System.out.println("number = " + number);
		}
	}
}


```
```
//3.5
package com.control.array;


public class ColonJump {

	public static void main(String[] args) {
		double[][] triangle = { { -2.0, 0.0 }, { 0.0, -1.0 }, { 2.0, 1.0 } };
		
		for (int i = 0; i < triangle.length; i++) {
			for (int j = 0; j < triangle[i].length; j++) {
				System.out.println("value = " + triangle[i][j]);
			}
		}
		
		for (int i = 0; i < triangle.length; i++) {
			boolean isFound = false; 
			for (int j = 0; j < triangle[i].length; j++) {
				if (triangle[i][j] == 0.0) {
					isFound = true; 
					System.out.println("simple found 0.0");
					break; 
				}
			}
			if (isFound) { 
				break; 
			}
		}
		
		loop1: for (int i = 0; i < triangle.length; i++) {
			for (int j = 0; j < triangle[i].length; j++) {
				if (triangle[i][j] == 0.0) { 
					System.out.println("loop1 found 0.0");
					break loop1; 
				}
			}
		}
		
		loop2: for (double[] dot : triangle) { 
			for (double coordinate : dot) { 
				if (coordinate == 0.0) { 
					System.out.println("loop2 found 0.0");
					break loop2; 
				}
			}
		}
	}
}


```
```
//3.6
package com.control.array;


public class OneDimensional2 {

	public static void main(String[] args) {
		
		int[] numbers = new int[] { 2, 3, 5, 7 };
		
		for (int i = 0; i < numbers.length; i++) {
			
			System.out.println("number = " + numbers[i]);
		}
	}
}


```
```
//3.7
package com.control.array;


public class OneDimensional3 {

	public static void main(String[] args) {
		
		int[] numbers = { 2, 3, 5, 7 };
		
		for (int i = 0; i < numbers.length; i++) {
			
			numbers[i]++;
			
			System.out.println("number = " + numbers[i]);
		}
	}
}


```
```
//3.8
package com.control.array;

public class TwoDimensional {

	public static void main(String[] args) {
		
		double triangle[][];
		
		triangle = new double[3][2];
		
		triangle[0][0] = -2.0;
		triangle[0][1] = 0.0;
		triangle[1][0] = 0.0;
		triangle[1][1] = -1.0;
		triangle[2][0] = 2.0;
		triangle[2][1] = 1.0;
		
		for (int i = 0; i < triangle.length; i++) {
			
			for (int j = 0; j < triangle[i].length; j++) {
				
				System.out.println("triangle[" + i + "][" + j + "]=" + triangle[i][j]);
			}
		}
	}
}


```
```
//3.9
package com.control.array;


public class TwoDimensional2 {

	public static void main(String[] args) {
		
		double[][] triangle = new double[][] { new double[] { -2.0, 0.0 },
				new double[] { 0.0, -1.0 }, new double[] { 2.0, 1.0 } };
		
		for (int i = 0; i < triangle.length; i++) {
			
			for (int j = 0; j < triangle[i].length; j++) {
				
				System.out.println("triangle[" + i + "][" + j + "]=" + triangle[i][j]);
			}
		}
	}
}


```
```
//3.10
package com.control.array;


public class TwoDimensional3 {

	public static void main(String[] args) {
		
		double[][] triangle = { { -2.0, 0.0 }, { 0.0, -1.0 }, { 2.0, 1.0 } };
		
		for (int i = 0; i < triangle.length - 1; i++) {
			for (int j = i + 1; j < triangle.length; j++) {
				
				double xDistance = Math.abs(triangle[j][0] - triangle[i][0]);
				
				double yDistance = Math.abs(triangle[j][1] - triangle[i][1]);
				
				double distance = Math.sqrt(xDistance * xDistance + yDistance * yDistance);
				System.out.println("i=" + i + ", j=" + j + ", distance=" + distance);
			}
		}
	}
}


```
```
//3.11
package com.control.logic;


public class Bool {

	public static void main(String[] args) {
		
		boolean zhen = true; 
		System.out.println("zhen=" + zhen);
		boolean jia = false; 
		System.out.println("jia=" + jia);
		
		boolean not = !zhen;
		System.out.println("not=" + not);
		
		boolean and = zhen & jia;
		System.out.println("and=" + and);
		
		boolean or = zhen | jia;
		System.out.println("or=" + or);
		
		boolean xor = zhen ^ jia;
		System.out.println("xor=" + xor);
		boolean value = true; 
		System.out.println("value=" + value);
		
		value &= false; 
		System.out.println("value=" + value);
		
		value |= true; 
		System.out.println("value=" + value);
		
		value ^= false; 
		System.out.println("value=" + value);
	}
}


```
```
//3.12
package com.control.logic;


public class Priority {

	public static void main(String[] args) {
		
		int fiveArithmetic = 7 + 5 - 4 * 6 / 3 % 9; 
		System.out.println("fiveArithmetic=" + fiveArithmetic);
		
		int negativeArithmetic = -8 / 4 + 2 * -3; 
		System.out.println("negativeArithmetic=" + negativeArithmetic);
		
		boolean greaterResult = 1 + 2 > 3 + 4; 
		System.out.println("greaterResult=" + greaterResult);
		boolean lessResult = 1 + 2 < 3 + 4; 
		System.out.println("lessResult=" + lessResult);
		
		boolean andResult = 1 > 2 & 3 < 4; 
		System.out.println("andResult=" + andResult);
		
		boolean orResult = 1 > 2 | 3 < 4;
		System.out.println("orResult=" + orResult);
		
		boolean xorResult = 1 > 2 ^ 3 < 4; 
		System.out.println("xorResult=" + xorResult);
		
		boolean zhen = true;
		boolean jia = false;
		boolean notResult = zhen == !jia; 
		System.out.println("notResult=" + notResult);
	}
}


```
```
//3.13
package com.control.logic;


public class Relation {

	public static void main(String[] args) {
		int seven = 7;
		int eight = 8;
		
		boolean equal = seven == eight; 
		System.out.println("equal=" + equal);
		
		boolean not_equal = seven != eight; 
		System.out.println("not_equal=" + not_equal);
		boolean greater = seven > eight;
		System.out.println("greater=" + greater);
		boolean less = seven < eight; 
		System.out.println("less=" + less);
		boolean greater_and_equal = seven >= eight; 
		System.out.println("greater_and_equal=" + greater_and_equal);
		boolean less_and_equal = seven <= eight; 
		System.out.println("less_and_equal=" + less_and_equal);
	}
}


```
```
//3.14
package com.control.logic;


public class ShortCircuit {

	public static void main(String[] args) {
		

		
		int andNumber = 1 + 2 & 3 + 4; 
		System.out.println("andNumber=" + andNumber);
		int orNumber = 1 + 2 | 3 + 4; 
		System.out.println("orNumber=" + orNumber);
		int xorNumber = 1 + 2 ^ 3 + 4; 
		System.out.println("xorNumber=" + xorNumber);
		
		
		boolean logicalResult = (1 & 2) > (3 | 4);
		System.out.println("logicalResult=" + logicalResult);
		int i = 1, j = 1;
		
		boolean result1 = 3 > 4 & ++i < 5;
		System.out.println("result1=" + result1 + ", i=" + i);
		
		boolean result2 = 3 > 4 && ++j < 5;
		System.out.println("result2=" + result2 + ", j=" + j);
	}
}


```
```
//3.15
package com.control.process;

import java.util.Scanner;


public class Condition {

	public static void main(String[] args) {
		System.out.println("凉风有信，秋月无边。打二字");
		System.out.println("获取“凉风有信”的谜底请按1，获取“秋月无边”的谜底请按2");
		Scanner scan = new Scanner(System.in); 
		int seq = scan.nextInt(); 
		if (seq == 1) { 
			System.out.println("凉风有信的谜底是“讽”");
		}
		if (seq == 2) { 
			System.out.println("秋月无边的谜底是“二”");
		}
	}
}


```
```
//3.16
package com.control.process;

import java.util.Scanner;


public class Condition2 {

	public static void main(String[] args) {
		System.out.println("凉风有信，秋月无边。打二字");
		System.out.println("获取“凉风有信”的谜底请按1，获取“秋月无边”的谜底请按2");
		Scanner scan = new Scanner(System.in); 
		int seq = scan.nextInt(); 

		seq = seq == 1 ? 1 : 2; 
		if (seq == 1) { 
			System.out.println("凉风有信的谜底是“讽”");
		}
		if (seq == 2) { 
			System.out.println("秋月无边的谜底是“二”");
		}
	}
}


```
```
//3.17
package com.control.process;

import java.util.Scanner;


public class Condition3 {

	public static void main(String[] args) {
		System.out.println("凉风有信，秋月无边。打二字");
		System.out.println("获取“凉风有信”的谜底请按1，获取“秋月无边”的谜底请按2");
		Scanner scan = new Scanner(System.in); 
		int seq = scan.nextInt(); 
		if (seq == 1) { 
			System.out.println("凉风有信的谜底是“讽”");
		} else { 
			System.out.println("秋月无边的谜底是“二”");
		}
	}
}


```
```
//3.18
package com.control.process;

import java.util.Scanner;


public class ForLoop {

	public static void main(String[] args) {
		System.out.println("长夜漫漫，无心睡眠，请给他设定一个睡醒的年限");
		Scanner scan = new Scanner(System.in); 
		int limit = scan.nextInt(); 
		int year;
		
		for (year = 0; year < limit; year++) {
			System.out.println("已经过去的年份：" + year);
		}
		
		System.out.println("他足足睡了这么多年：" + year);
	}
}


```
```
//3.19
package com.control.process;

import java.util.Scanner;


public class ForLoop2 {

	public static void main(String[] args) {
		System.out.println("长夜漫漫，无心睡眠，请给他设定一个睡醒的年限");
		Scanner scan = new Scanner(System.in); 
		int limit = scan.nextInt(); 
		for (int year = 0;; year++) {
			System.out.println("已经过去的年份：" + year);
			if (year >= limit) { 
				System.out.println("他足足睡了这么多年：" + year);
				break; 
			} else {
				continue; 
			}
		}
	}
}


```
```
//3.20
package com.control.process;

import java.util.Scanner;


public class ForLoop3 {

	public static void main(String[] args) {
		System.out.println("长夜漫漫，无心睡眠，请给他设定一个睡醒的年限");
		Scanner scan = new Scanner(System.in); 
		int limit = scan.nextInt(); 
		int year = 0; 
		for (;;) { 
			System.out.println("已经过去的年份：" + year);
			if (year >= limit) { 
				System.out.println("他足足睡了这么多年：" + year);
				break; 
			} else {
				year++; 
				continue;
			}
		}
	}
}


```
```
//3.21
package com.control.process;

import java.util.Scanner;


public class Multipath {

	public static void main(String[] args) {
		System.out.println("凉风有信，秋月无边。打二字");
		System.out.println("获取“凉风有信”的谜底请按1，获取“秋月无边”的谜底请按2");
		Scanner scan = new Scanner(System.in); 
		int seq = scan.nextInt(); 
		if (seq == 1) { 
			System.out.println("凉风有信的谜底是“讽”");
		} else if (seq == 2) { 
			System.out.println("秋月无边的谜底是“二”");
		} else { 
			System.out.println("您的按键有误");
		}
	}
}


```
```
//3.22
package com.control.process;

import java.util.Scanner;


public class Multipath2 {

	public static void main(String[] args) {
		System.out.println("凉风有信，秋月无边。打二字");
		System.out.println("获取“凉风有信”的谜底请按1，获取“秋月无边”的谜底请按2");
		Scanner scan = new Scanner(System.in); 
		int seq = scan.nextInt(); 
		
		switch (seq) {
		case 1:
			System.out.println("凉风有信的谜底是“讽”");
			break; 
		case 2: 
			System.out.println("秋月无边的谜底是“二”");
			break; 
		default: 
			System.out.println("您的按键有误");
			break; 
		}
		System.out.println("猜谜结束");
	}
}


```
```
//3.23
package com.control.process;

import java.util.Scanner;


public class WhileLoop {

	public static void main(String[] args) {
		System.out.println("长夜漫漫，无心睡眠，请给他设定一个睡醒的年限");
		Scanner scan = new Scanner(System.in); 
		int limit = scan.nextInt(); 
		int year = 0;
		while (year < limit) { 
			System.out.println("已经过去的年份：" + year);
			year++;
		}
		System.out.println("他足足睡了这么多年：" + year);
	}
}


```
```
//3.24
package com.control.process;

import java.util.Scanner;


public class WhileLoop2 {

	public static void main(String[] args) {
		System.out.println("长夜漫漫，无心睡眠，请给他设定一个睡醒的年限");
		Scanner scan = new Scanner(System.in); 
		int limit = scan.nextInt(); 
		int year = 0;
		do { 
			System.out.println("已经过去的年份：" + year);
			year++;
		} while (year < limit); 
		System.out.println("他足足睡了这么多年：" + year);
	}
}


```
```
//3.25
package com.control.process;

import java.util.Scanner;


public class WhileLoop3 {

	public static void main(String[] args) {
		System.out.println("长夜漫漫，无心睡眠，请给他设定一个睡醒的年限");
		Scanner scan = new Scanner(System.in);
		int limit = scan.nextInt(); 
		int year = 0;
		while (true) { 
			System.out.println("已经过去的年份：" + year);
			if (year < limit) { 
				year++;
				continue; 
			} else {
				break; 
			}
		}
		System.out.println("他足足睡了这么多年：" + year);
	}
}


```
```
//3.26
package com.control;

import java.util.Arrays;
import java.util.Random;


public class BinaryChop {

	public static void main(String[] args) {
		int item = 0; 
		int[] numbers = new int[20]; 
		
		loop: for (int i = 0; i < numbers.length; i++) {
			item = new Random().nextInt(100);
			for (int j = 0; j < i; j++) { 
				if (numbers[j] == item) { 
					i--; 
					continue loop; 
				}
			}
			numbers[i] = item; 
		}
		Arrays.sort(numbers); 
		for (int seq=0; seq<numbers.length; seq++) { 
			System.out.println("序号="+seq+", 数字="+numbers[seq]);
		}
		System.out.println("最后生成的随机数="+item);

		
		int aim_item = item; 
		System.out.println("准备查找的目标数字="+aim_item);
		int start = 0; 
		int end = numbers.length - 1; 
		int middle = 0; 
		for (int count = 1, position = -1; start <= end; count++) {
			middle = (start + end) / 2; 
			System.out.println("折半查找的中间数字="+numbers[middle]);
			if (numbers[middle] > aim_item) {
				
				end = middle - 1;
			} else if (numbers[middle] < aim_item) {
				
				start = middle + 1;
			} else { 
				position = middle;
				System.out.println("查找次数="+count+", 序号位置="+position);
				break;
			}
		}
	}
}


```
```
//3.27
package com.control;


public class Feibonaqi {

	public static void main(String[] args) {
		int[] rabbitNumbers; 
		rabbitNumbers = new int[12]; 
		
		for (int i = 0; i < rabbitNumbers.length; i++) {
			if (i < 2) { 
				rabbitNumbers[i] = 1;
			} else { 
				rabbitNumbers[i] = rabbitNumbers[i - 2] + rabbitNumbers[i - 1];
			}
			int month = i + 1;
			
			System.out.println("第" + month + "个月，兔子对数=" + rabbitNumbers[i]);
		}
	}
}


```
```
//3.28
package com.control;


public class Geligaoli {

	public static void main(String[] arg) {
		double π = 0; 
		double zhengfu = 1; 
		for (int i=1; i<800000; i+=2) { 
			π = π + zhengfu*4/i; 
			zhengfu = -zhengfu; 
		}
		System.out.println("圆周率="+π);
	}

}


```
```
//3.29
package com.control;


public class Jitutonglong {

	public static void main(String[] arg) {
		
		int chick, rabbit; 
		int sum = 35; 
		for (chick=0, rabbit=0; chick <= sum; chick++) {
			rabbit = sum - chick; 
			if (chick * 2 + rabbit * 4 == 94) { 
				break;
			}
		}
		System.out.println("鸡的数量为" + chick + "，兔子的数量为" + rabbit);
	}
}


```
```
//3.30
package com.control;

import java.util.Arrays;

public class SunziDingli {

	public static void main(String[] arg) {
		
		int count = 0; 
		int[] numbers = new int[0]; 
		for (int i = 1; i < 1000; i++) { 
			if (i%3==2 && i%5==3 && i%7==2) { 
				count++; 
				numbers = Arrays.copyOf(numbers, count); 
				numbers[count-1] = i; 
			}
		}
		for (int number : numbers) { 
			System.out.println("符合孙子定理的整数number=" + number);
		}
	}

}


```
```
//3.31
package com.control;


public class YanghuiSanjiao {
	
	public static void main(String[] args) {
		int MAX_ROW = 10; 
	
		int[][] triangles = new int[MAX_ROW][];
		for (int i = 0; i < MAX_ROW; i++) {
			triangles[i] = new int[i + 1]; 
		}

		for (int i = 0; i < triangles.length; i++) { 
			for (int j = 0; j < triangles[i].length; j++) {
				if (j==0 || j==triangles[i].length-1) { 
					triangles[i][j] = 1;
				} else { 
					triangles[i][j] = triangles[i-1][j-1] + triangles[i-1][j];
				}
			}
		}

		for (int[] row : triangles) { 
			for (int number : row) {
				System.out.printf("%5d", number); 
			}
			System.out.println(); 
		}
	}
}


```
# 第4章 方法與 wrapper包裝
```
//4.1
package com.method.big;

import java.math.BigDecimal;
import java.math.MathContext;
import java.math.RoundingMode;


public class TestDecimal {

	public static void main(String[] args) {
		BigDecimal sevenAndHalf = BigDecimal.valueOf(7.5); 
		BigDecimal three = BigDecimal.valueOf(3); 
		BigDecimal sum = sevenAndHalf.add(three); 
		System.out.println("sum="+sum);
		BigDecimal sub = sevenAndHalf.subtract(three); 
		System.out.println("sub="+sub);
		BigDecimal mul = sevenAndHalf.multiply(three);
		System.out.println("mul="+mul);
		BigDecimal div = sevenAndHalf.divide(three); 
		System.out.println("div="+div);
		BigDecimal remainder = sevenAndHalf.remainder(three); 
		System.out.println("remainder="+remainder);
		BigDecimal neg = sevenAndHalf.negate(); 
		System.out.println("neg="+neg);
		BigDecimal abs = sevenAndHalf.abs(); 
		System.out.println("abs="+abs);
		BigDecimal pow = sevenAndHalf.pow(2); 
		System.out.println("pow="+pow);
		
		
		testDivide();
	}

	
	private static void testDivide() {
		
		BigDecimal one = BigDecimal.valueOf(100);
		BigDecimal three = BigDecimal.valueOf(3);
		
		BigDecimal div = one.divide(three, 64, BigDecimal.ROUND_HALF_UP);
		System.out.println("div="+div);
		
		MathContext mc = new MathContext(64, RoundingMode.HALF_UP);
		BigDecimal divByMC = one.divide(three, mc); 
		System.out.println("divByMC="+divByMC);
	}

}


```
```
//4.2
package com.method.big;

import java.math.BigInteger;


public class TestInteger {

	public static void main(String[] args) {
		BigInteger nine = BigInteger.valueOf(9); 
		BigInteger four = BigInteger.valueOf(4); 
		BigInteger sum = nine.add(four); 
		System.out.println("sum="+sum);
		BigInteger sub = nine.subtract(four); 
		System.out.println("sub="+sub);
		BigInteger mul = nine.multiply(four);
		System.out.println("mul="+mul);
		BigInteger div = nine.divide(four); 
		System.out.println("div="+div);
		BigInteger remainder = nine.remainder(four);
		System.out.println("remainder="+remainder);
		BigInteger neg = nine.negate(); 
		System.out.println("neg="+neg);
		BigInteger abs = nine.abs(); 
		System.out.println("abs="+abs);
		BigInteger pow = nine.pow(2);
		System.out.println("pow="+pow);
	}

}


```
```
//4.3
package com.method.function;

import java.util.Date;


public class Input {

	public static void main(String[] args) {
		showTime(); 
		
		setAlarm(1); 
		setAlarm(1, -10); 
		
		setAlarm(); 
		setAlarm(1, -10, 3); 
		int[] addedArray = {1, -10, 3};
		setAlarmByArray(addedArray); 
	}
	
	
	private static void showTime() {
		Date date = new Date(); 
		int hour = date.getHours(); 
		int minute = date.getMinutes(); 
		int second = date.getSeconds();
		System.out.println("当前时间是"+hour+"时"+minute+"分"+second+"秒");
	}
	
	
	private static void setAlarm(int addedHour) {
		Date date = new Date(); 
		int hour = date.getHours()+addedHour; 
		int minute = date.getMinutes(); 
		int second = date.getSeconds(); 
		System.out.println("设定的闹钟时间是"+hour+"时"+minute+"分"+second+"秒");
	}

	
	private static void setAlarm(int addedHour, int addedMinute) {
		Date date = new Date(); 
		int hour = date.getHours()+addedHour; 
		int minute = date.getMinutes()+addedMinute; 
		int second = date.getSeconds(); 
		System.out.println("设定的闹钟时间是"+hour+"时"+minute+"分"+second+"秒");
	}
	
	private static void setAlarm(int... addedNumber) {
		Date date = new Date(); 
		int hour = date.getHours(); 
		int minute = date.getMinutes(); 
		int second = date.getSeconds(); 
		
		if (addedNumber.length > 0) { 
			hour += addedNumber[0];
		}
		if (addedNumber.length > 1) { 
			minute += addedNumber[1];
		}
		if (addedNumber.length > 2) { 
			second += addedNumber[2];
		}
		System.out.println("可变参数设定的闹钟时间是"+hour+"时"+minute+"分"+second+"秒");
	}
	
	
	private static void setAlarmByArray(int[] addedNumber) {
		Date date = new Date(); 
		int hour = date.getHours(); 
		int minute = date.getMinutes(); 
		int second = date.getSeconds(); 
		if (addedNumber.length > 0) { 
			hour += addedNumber[0];
		}
		if (addedNumber.length > 1) { 
			minute += addedNumber[1];
		}
		if (addedNumber.length > 2) { 
			second += addedNumber[2];
		}
		System.out.println("设定的闹钟时间是"+hour+"时"+minute+"分"+second+"秒");
	}
}


```
```
//4.4
package com.method.function;


public class Output {

	public static void main(String[] args) {
		
		printNsquareRoot(2, 2); 
		
		double number1 = 3;
		int n1 = 2;
		double nsquareRoot = getNsquareRoot(number1, n1);
		System.out.println(number1+"的"+n1+"次方根="+nsquareRoot);
		
		double number2 = 3;
		int n2 = 2;
		double[] rootArray = getNsquareRootArray(number2, n2);
		for (double root : rootArray) {
			System.out.println(number2+"的"+n2+"次方根="+root);
		}
	}
	
	
	
	private static void printNsquareRoot(double number, int n) {
		if (n <= 0) {
			System.out.println("n必须为自然数");
			return; 
		} else if (n%2==0 && number<0) {
			System.out.println("不能对负数开偶次方根");
			return; 
		}
		
		double nsquareRoot = number;
		for (int i=0; i<n*2; i++) { 
			double slope = n * Math.pow(nsquareRoot, n-1); 
			nsquareRoot = nsquareRoot - (Math.pow(nsquareRoot, n)-number)/slope;
		}
		System.out.println(number+"的"+n+"次方根="+nsquareRoot);
		
	}
	
	
	private static double getNsquareRoot(double number, int n) {
		if (n <= 0) {
			System.out.println("n必须为自然数");
			return 0; 
		} else if (n%2==0 && number<0) {
			System.out.println("不能对负数开偶次方根");
			return 0; 
		}
		
		double nsquareRoot = number;
		for (int i=0; i<n*2; i++) { 
			double slope = n * Math.pow(nsquareRoot, n-1); 
			nsquareRoot = nsquareRoot - (Math.pow(nsquareRoot, n)-number)/slope;
		}
		return nsquareRoot; 
	}

	
	private static double[] getNsquareRootArray(double number, int n) {
		if (n <= 0) {
			System.out.println("n必须为自然数");
			return new double[]{}; 
		} else if (n%2==0 && number<0) {
			System.out.println("不能对负数开偶次方根");
			return new double[]{}; 
		}
		
		double nsquareRoot = number;
		for (int i=0; i<n*2; i++) { 
			double slope = n * Math.pow(nsquareRoot, n-1); 
			nsquareRoot = nsquareRoot - (Math.pow(nsquareRoot, n)-number)/slope;
		}
		double[] rootArray; 
		if (n%2 == 0) {
			rootArray = new double[]{nsquareRoot, -nsquareRoot};
		} else { 
			rootArray = new double[]{nsquareRoot};
		}
		return rootArray; 
	}
	
}


```
```
//4.5
package com.method.function;


public class Simple {

	
	public static void main(String[] args) { 
		if (args.length == 0) {
			System.out.println("您没有输入任何参数");
		}
		for (int i=0; i<args.length; i++) { 
			int seq = i+1;
			System.out.println("您输入的第"+seq+"个参数是："+args[i]);
		}
	}
}


```
```
//4.6
package com.method.pack;


public class PackBoolean {

	public static void main(String[] args) {
		
		Boolean boolPack = true;
		
		
		System.out.println("boolPack="+boolPack);
		
		boolean bool = boolPack.booleanValue();
		System.out.println("bool="+bool);

		
		Boolean boolZhen = true;
		Boolean boolJia = true;
		Boolean not = !boolZhen;
		System.out.println("not="+not);
		Boolean and = boolZhen & boolJia;
		System.out.println("and="+and);
		Boolean or = boolZhen | boolJia;
		System.out.println("or="+or);
		Boolean xor = boolZhen ^ boolJia;
		System.out.println("xor="+xor);
		boolean equalResult = boolPack.equals(false); 
		System.out.println("equalResult="+equalResult);
		
		boolean a = true, b = false;
		
		boolean andResult = Boolean.logicalAnd(a, b);
		System.out.println("andResult="+andResult);
		
		boolean orResult = Boolean.logicalOr(a, b);
		System.out.println("orResult="+orResult);
		
		boolean xorResult = Boolean.logicalXor(a, b);
		System.out.println("xorResult="+xorResult);
	}
}


```
```
//4.7
package com.method.pack;


public class PackNumber {

	public static void main(String[] args) {
		
		Integer oneInteger = 1;
		
		System.out.println("oneInteger="+oneInteger);
		byte oneByte = oneInteger.byteValue(); 
		System.out.println("oneByte="+oneByte);
		short oneShort = oneInteger.shortValue(); 
		System.out.println("oneShort="+oneShort);
		int oneInt = oneInteger.intValue(); 
		System.out.println("oneInt="+oneInt);
		long oneLong = oneInteger.longValue(); 
		System.out.println("oneLong="+oneLong);
		float oneFloat = oneInteger.floatValue(); 
		System.out.println("oneFloat="+oneFloat);
		double oneDouble = oneInteger.doubleValue(); 
		System.out.println("oneDouble="+oneDouble);
	}
}


```
```
//4.8
package com.method.pack;


public class PackOperation {

	public static void main(String[] args) {
		
		Integer five = Integer.valueOf(5);
		Integer three = Integer.valueOf(3);
		Integer plus = five + three;
		System.out.println("plus="+plus);
		Integer minus = five - three;
		System.out.println("minus="+minus);
		Integer multiply = five * three;
		System.out.println("multiply="+multiply);
		Integer divide = five / three;
		System.out.println("divide="+divide);
		Integer remainer = five % three;
		System.out.println("remainer="+remainer);
		
		Integer oneInteger = 1;
		boolean equalResult = oneInteger.equals(2); 
		System.out.println("equalResult="+equalResult);
		Integer ten1=10, ten2=10; 
		boolean equalTen = (ten1==ten2); 
		System.out.println("equalTen="+equalTen);
		Integer thousand1=1000, thousand2=1000;
		boolean equalThousand = (thousand1==thousand2); 
		System.out.println("equalThousand="+equalThousand);

		int a = 7, b = 8;
		int sum = Integer.sum(a, b); 
		System.out.println("sum="+sum);
		int max = Integer.max(a, b); 
		System.out.println("max="+max);
		int min = Integer.min(a, b); 
		System.out.println("min="+min);
		
		int compareResult = Integer.compare(a, b);
		System.out.println("compareResult="+compareResult);
	}

}


```
```
//4.9
package com.method;

import java.math.BigDecimal;
import java.math.MathContext;
import java.math.RoundingMode;


public class BigNewton {

	public static void main(String[] arg) {
		
		testSqrtByBigDecimal(); 
	}

	
	private static void testSqrtByDouble() {
		double number = 2; 
		double root = sqrtByDouble(number); 
		System.out.println("双精度数开方运算，原始数字=" + number + ", 它的平方根=" + root);
	}

	
	private static void testSqrtByDouble2() {
		double number = 2; 
		double root = sqrtByDoubleWithDo(number); 
		System.out.println("双精度数开方运算，原始数字=" + number + ", 它的平方根=" + root);
	}

	
	private static void testSqrtByBigDecimal() {
		BigDecimal number = BigDecimal.valueOf(2);
		
		BigDecimal root = sqrtByBigDecimal(number, 100); 
		System.out.println("大小数开方运算，原始数字=" + number + ", 它的平方根=" + root);
	}

	
	private static double sqrtByDouble(double number) {
		double Xm = number; 
		while (true) {
			double lastXm = Xm; 
			Xm = (Xm + number/Xm) / 2;
			
			if (Xm >= lastXm) {
				break;
			}
		}
		return Xm;
	}

	
	private static double sqrtByDoubleWithDo(double number) {
		double Xm = number; 
		double lastXm = Xm; 
		do {
			lastXm = Xm; 
			Xm = (Xm + number/Xm) / 2; 
		} while (Xm < lastXm); 
		return Xm;
	}

	
	private static BigDecimal sqrtByBigDecimal(BigDecimal number, int precision) {
		BigDecimal two = BigDecimal.valueOf(2);
		
		MathContext mc = new MathContext(precision, RoundingMode.HALF_UP);
		if (number.compareTo(BigDecimal.ZERO) <= 0) { 
			return BigDecimal.valueOf(0);
		} else {
			BigDecimal X = number; 
			
			while (true) {
				
				BigDecimal Xm = (X.add(number.divide(X, mc))).divide(two, mc);
				
				if (X.equals(Xm)) {
					break;
				}
				X = Xm; 
			}
			return X;
		}
	}

}


```
```
//4.10
package com.method;

import java.math.BigDecimal;
import java.math.BigInteger;
import java.math.MathContext;
import java.math.RoundingMode;


public class ExactPai {

	public static void main(String[] arg) {
		calculateByDouble(); 
		calculateByBigDecimal(); 
	}

	
	private static void calculateByDouble() {
		int n = 60; 
		long edgeNumber = (long) (Math.pow(2, 60) * 6);
		System.out.println("割圆次数=" + n + ", 内接正N边形的边数=" + edgeNumber);
		
		double π_rough = getPaiRough(n);
		System.out.println("粗略的圆周率数值=" + π_rough);
	}

	
	private static void calculateByBigDecimal() {
		int n = 165;
		BigInteger edgeNumber = BigInteger.valueOf(2).pow(n).multiply(BigInteger.valueOf(6));
		System.out.println("割圆次数=" + n + ", 内接正N边形的边数=" + edgeNumber);
		
		BigDecimal π_exact = getPaiExact(n);
		System.out.println("精确的圆周率数值=" + π_exact);
	}

	
	private static double getPaiRough(int n) {
		int r = 1; 
		int d = 2 * r; 
		double edgeLength = r; 
		long edgeNumber = 6L; 
		double π = edgeLength * edgeNumber / d; 
		for (int i = 0; i < n; i++) { 
			edgeNumber = edgeNumber * 2; 
			double gou = edgeLength / 2.0; 
			double gu = r - Math.sqrt(Math.pow(r, 2) - Math.pow(gou, 2)); 
			edgeLength = Math.sqrt(Math.pow(gou, 2) + Math.pow(gu, 2));
			
			π = edgeLength * edgeNumber / d;
		}
		return π;
	}

	
	private static BigDecimal getPaiExact(int n) {
		BigDecimal two = BigDecimal.valueOf(2.0);
		BigDecimal r = BigDecimal.valueOf(1);
		BigDecimal d = r.multiply(two); 
		BigDecimal edgeLength = r; 
		BigDecimal edgeNumber = BigDecimal.valueOf(6); 
		BigDecimal π = edgeLength.multiply(edgeNumber).divide(d); 
		int precision = 110; 
		
		MathContext mc = new MathContext(precision, RoundingMode.HALF_UP);
		for (int i = 0; i < n; i++) { 
			edgeNumber = edgeNumber.multiply(two); 
			BigDecimal gou = edgeLength.divide(two, mc); 
			BigDecimal gu = r.subtract(sqrt(r.pow(2).subtract(gou.pow(2)), precision)); 
			
			edgeLength = sqrt(gu.pow(2).add(gou.pow(2)), precision);
			
			π = edgeLength.multiply(edgeNumber).divide(d, mc);
		}
		return π;
	}

	
	private static BigDecimal sqrt(BigDecimal number, int precision) {
		BigDecimal two = BigDecimal.valueOf(2);
		
		MathContext mc = new MathContext(precision, RoundingMode.HALF_UP);
		if (number.compareTo(BigDecimal.ZERO) <= 0) { 
			return BigDecimal.valueOf(0);
		} else {
			BigDecimal X = number; 
			while (true) {
				
				BigDecimal Xm = (X.add(number.divide(X, mc))).divide(two, mc);
				
				if (X.equals(Xm)) {
					break;
				}
				X = Xm; 
			}
			return X;
		}
	}

}


```
```
//4.11
package com.method;

import java.math.BigInteger;


public class RecursionFactorial {

	public static void main(String[] arg) {
		calculateFactorialByLong(); 
		calculateFactorialByBigInteger(); 
	}

	
	private static void calculateFactorialByLong() {
		int n = 20;
		
		long resultLong = factorialSimplify(n);
		System.out.println(n+"!的长整数阶乘结果="+resultLong);
	}

	
	private static void calculateFactorialByBigInteger() {
		int n = 100;
		
		BigInteger resultBig = factorialBig(n);
		System.out.println(n+"!的大整数阶乘结果="+resultBig);
	}

	
	private static long factorialRepeat(int n) {
		long result = n;
		for (int i = n - 1; i > 1; i--) {
			result = result * i; 
		}
		return result;
	}

	
	private static long factorialRecursion(int n) {
		if (n <= 1) { 
			return n;
		} else { 
			return n * factorialRecursion(n - 1);
		}
	}

	
	private static long factorialSimplify(int n) {
		return (n <= 1) ? n : n * factorialSimplify(n - 1);
	}

	
	private static BigInteger factorialBig(int n) {
		BigInteger bigN = BigInteger.valueOf(n); 
		return (n <= 1) ? bigN : bigN.multiply(factorialBig(n - 1));
	}

}

```

# 第5章字串與正則表達式

```
//5.1
package com.string.character;

public class intToChar {

	public static void main(String[] arg) {
		charToInt();
		intToChar();
		printCapital();
	
	}

	private static void charToInt() {
		int a = 'A'; 
		System.out.println("int a=" + a);
		int tian = '田'; 
		System.out.println("int tian=" + tian);
	}

	
	private static void intToChar() {
		char a = 65; 
		System.out.println("char a=" + a);
		char tian = 30000; 
		System.out.println("char tian=" + tian);
		
		char begin = 0x3000;
		System.out.println("chinese begin=" + begin);
		char end = 0x9FFF;
		System.out.println("chinese end=" + end);
		char max = 65535; 
		System.out.println("char max=" + max);
	}

	
	private static void printCapital() {
		char a = 'A';
		for (int i = 0; i < 26; i++) { 
			
			char capital = (char) (a + i);
			System.out.println("capital=" + capital);
		}
	}

	private static void printCapital2() {
		int a = 65;
		for (int i = 0; i < 26; i++) {
			char capital = (char) (a + i);
			System.out.println("capital=" + capital);
		}
	}

}


```
```
//5.2
package com.string.character;


public class PackChar {

	public static void main(String[] arg) {
		Character character = 'A'; 
		System.out.println("character=" + character);
		char value = character.charValue(); 
		System.out.println("value=" + value);
	
		Character plusResult = (char) (character + 1);
		System.out.println("plusResult=" + plusResult);

		Character letter = 'A'; 
	
		boolean isDigit = Character.isDigit(letter); 
		System.out.println("isDigit=" + isDigit);
		boolean isLetter = Character.isLetter(letter);
		System.out.println("isLetter=" + isLetter);
		boolean isLowerCase = Character.isLowerCase(letter); 
		System.out.println("isLowerCase=" + isLowerCase);
		boolean isUpperCase = Character.isUpperCase(letter); 
		System.out.println("isUpperCase=" + isUpperCase);
		Character line = '\n'; 
		boolean isSpaceChar = Character.isSpaceChar(line);
		System.out.println("isSpaceChar=" + isSpaceChar);
	
		boolean isWhitespace = Character.isWhitespace(line);
		System.out.println("isWhitespace=" + isWhitespace);
		char lowerCase = Character.toLowerCase(letter); 
		System.out.println("lowerCase=" + lowerCase);
		char upperCase = Character.toUpperCase(letter); 
		System.out.println("upperCase=" + upperCase);
	}
}


```
```
//5.3
package com.string.character;


public class TypeChar {

	public static void main(String[] arg) {
		char a = 'A';
		System.out.println("a=" + a);
		char tian = '田'; 
		System.out.println("tian=" + tian);
		char one = '1'; 
		System.out.println("one=" + one);
		char[] array = new char[]{'A', 'B', 'C'}; 
		
		for (char item : array) { 
			System.out.println("item=" + item);
		}
		
		char tab = '\t'; 
		System.out.println("tab=" + tab);
		char enter = '\r';
		System.out.println("enter=" + enter);
		char line = '\n'; 
		System.out.println("line=" + line);
		char singleQuote = '\''; 
		System.out.println("singleQuote=" + singleQuote);
		char doubleQuote = '\"'; 
		System.out.println("doubleQuote=" + doubleQuote);
		char reverseTilt = '\\'; 
		System.out.println("reverseTilt=" + reverseTilt);
	}
}


```
```
//5.4
package com.string.regular;


public class RegexMatch {

	public static void main(String[] arg) {
		String phone = "13901234567";
		
		boolean isPhone = isPhone(phone);
		System.out.println("phone = " + phone + ", isPhone = " + isPhone);
		
		checkLastFour(); 
		String icno = "350111199801011231";
		
		boolean isICNO = isICNO(icno);
		System.out.println("icno = " + icno + ", isICNO = " + isICNO);
		String email = "aqi88@163.com";
		
		boolean isEmail = isEmail(email);
		System.out.println("email = " + email + ", isEmail = " + isEmail);
	}

	
	public static boolean isPhone(String phone) {
		
		String regex = "1[3-9]\\d{9}";
	
		return phone.matches(regex);
	}

	
	public static void checkYear() {
		String regex = "(19|20)\\d{2}"; 
		for (int i = 1899; i <= 2100; i++) {
			if (i > 1910 && i < 2090) { 
				continue;
			}
			String year = i + "";
			boolean check = year.matches(regex);
			System.out.println("year = " + year + ", check = " + check);
		}
	}

	
	public static void checkMonth() {
		String regex = "0[1-9]|1[0-2]"; 
		for (int i = 0; i <= 13; i++) {
			String month = String.format("%02d", i);
			boolean check = month.matches(regex); 
			System.out.println("month = " + month + ", check = " + check);
		}
	}

	
	public static void checkDay() {
		String regex = "0[1-9]|[12]\\d|3[01]";
		for (int i = 0; i <= 32; i++) {
			String day = String.format("%02d", i);
			boolean check = day.matches(regex); 
			System.out.println("day = " + day + ", check = " + check);
		}
	}

	
	public static void checkLastFour() {
		String regex = "\\d{3}([0-9xX])"; 
		for (int i = 0; i < 36; i++) { 
			char last;
			if (i < 10) { 
				last = (char) ('0' + i);
			} else { 
				last = (char) ('A' + i - 10); 
			}
			String lastFour = String.format("%03d%c", i * 13, last);
			boolean check = lastFour.matches(regex);
			System.out.println("lastFour = " + lastFour + ", check = " + check);
		}
	}

	
	public static boolean isICNO(String icno) {
		
		String regex = "(\\d{6})((19|20)\\d{2})(0[1-9]|1[0-2])(0[1-9]|[12]\\d|3[01])(\\d{3}([0-9xX]))";
		return icno.matches(regex);
	}

	
	public static boolean isEmail(String email) {
		String regex = "([a-zA-Z0-9_\\-\\.]+)@((\\[[0-9]{1,3}\\.[0-9]{1,3}\\.[0-9]{1,3}\\.)|(([a-zA-Z0-9\\-]+\\.)+))([a-zA-Z]{2,4}|[0-9]{1,3})(\\]?)";
		return email.matches(regex);
	}

}


```
```
//5.5
package com.string.regular;


public class RegexSplit {

	public static void main(String[] arg) {
		
		splitByComma();
		
		splitBySpace();
		
		splitByDot();
		
		splitByLine();
		
		splitByMixture();
		
		splitByArith();
		
		splitByBracket();
		
		splitWithPlus();
		
		splitWithStar();
	
		splitWithLetter();
		
		splitWithDot();
	}


	private static void splitByComma() {
		String commaStr = "123,456,789";
		String[] commaArray = commaStr.split(",");
		for (String item : commaArray) { 
			System.out.println("comma item = " + item);
		}
	}

	
	private static void splitBySpace() {
		String spaceStr = "123 456 789";
		String[] spaceArray = spaceStr.split(" "); 
		for (String item : spaceArray) {
			System.out.println("space item = " + item);
		}
	}

	
	private static void splitByDot() {
		String dotStr = "123.456.789";
		
		String[] dotArray = dotStr.split("\\.");
		for (String item : dotArray) { 
			System.out.println("dot item = " + item);
		}
	}

	
	private static void splitByLine() {
		String lineStr = "123|456|789";
		
		String[] lineArray = lineStr.split("\\|");
		for (String item : lineArray) {
			System.out.println("line item = " + item);
		}
	}

	
	private static void splitByMixture() {
		String mixtureStr = "123,456 789";
		
		String[] mixtureArray = mixtureStr.split(",| ");
		for (String item : mixtureArray) { 
			System.out.println("mixture item = " + item);
		}
	}

	
	private static void splitByArith() {
		String arithStr = "123+456*789-123/456%789";
		
		String[] arithArray = arithStr.split("\\+|\\*|\\-|/|%");
		for (String item : arithArray) {
			System.out.println("arith item = " + item);
		}
	}

	
	private static void splitByBracket() {
		String bracketStr = "(1)123;(2)456;(3)789;";
		
		String[] bracketArray = bracketStr.split("\\(\\d\\)");
		for (String item : bracketArray) {
			System.out.println("bracket item = " + item);
		}
	}

	
	private static void splitWithPlus() {
		String bracketStr = "(1)123;(2)456;(13)789;";
	
		String[] bracketArray = bracketStr.split("\\(\\d+\\)");
		for (String item : bracketArray) {
			System.out.println("plus item = " + item);
		}
	}

	
	private static void splitWithStar() {
		String bracketStr = "()123;(2)456;(13)789;";
		
		String[] bracketArray = bracketStr.split("\\(\\d*\\)");
		for (String item : bracketArray) { 
			System.out.println("star item = " + item);
		}
	}

	
	private static void splitWithLetter() {
		String bracketStr = "(a)123;(B)456;(c)789;";
		
		String[] bracketArray = bracketStr.split("\\([a-zA-Z]\\)");
		for (String item : bracketArray) { 
			System.out.println("letter item = " + item);
		}
	}

	
	private static void splitWithDot() {
		String bracketStr = "(1)123;(B)456;(%)789;";
		
		String[] bracketArray = bracketStr.split("\\(.\\)");
		for (String item : bracketArray) { 
			System.out.println("dot item = " + item);
		}
	}

}


```
```
//5.6
package com.string.string;

import java.math.BigDecimal;
import java.math.BigInteger;


public class StrAssign {

	public static void main(String[] arg) {
		
		String fromQuote = "Hello";
		System.out.println("fromQuote=" + fromQuote);
		
		String fromValueOf = String.valueOf(111);
		System.out.println("fromValueOf=" + fromValueOf);
		
		char[] array = { 'A', 'B', 'C' };
		String fromArray = new String(array);
		System.out.println("fromArray=" + fromArray);
		
		String fromPlus = true + "";
		System.out.println("fromPlus=" + fromPlus);

		String number = "13456";
		Integer packInt = Integer.parseInt(number); 
		System.out.println("packInt=" + packInt);
		Long packLong = Long.parseLong(number); 
		System.out.println("packLong=" + packLong);
		Float packFloat = Float.parseFloat(number); 
		System.out.println("packFloat=" + packFloat);
		Double packDouble = Double.parseDouble(number);
		System.out.println("packDouble=" + packDouble);
		String zhen = "true";
		Boolean packBoolean = Boolean.parseBoolean(zhen);
		System.out.println("packBoolean=" + packBoolean);
		char[] numberArray = number.toCharArray();
		for (char item : numberArray) { 
			System.out.println("item=" + item);
		}

		String bigNumber = "134567890134567890134567890";
		BigInteger bigInt = new BigInteger(bigNumber); 
		System.out.println("bigInt=" + bigInt);
		BigDecimal bigDec = new BigDecimal(bigNumber); 
		System.out.println("bigDec=" + bigDec);

		
		System.out.println("packInt toString=" + packInt.toString());
		System.out.println("packLong toString=" + packLong.toString());
		System.out.println("packFloat toString=" + packFloat.toString());
		System.out.println("packDouble toString=" + packDouble.toString());
		System.out.println("packBoolean toString=" + packBoolean.toString());
		System.out.println("bigInt toString=" + bigInt.toString());
		System.out.println("bigDec toString=" + bigDec.toString());
	}
}


```
```
//5.7
package com.string.string;

import java.math.BigDecimal;
import java.math.RoundingMode;

public class StrFormat {

	public static void main(String[] arg) {
	
		String fromString = String.format("格式化子串的字符串：%s", "Hello");
		System.out.println("fromString=" + fromString);
		
		String fromChar = String.format("格式化字符的字符串：%c", 'A');
		System.out.println("fromChar=" + fromChar);
	
		String fromBoolean = String.format("格式化布尔值的字符串：%b", false);
		System.out.println("fromBoolean=" + fromBoolean);
	
		String fromInt = String.format("格式化整型数的字符串：%d", 255);
		System.out.println("fromInt=" + fromInt);
		
		String fromOct = String.format("格式化十六进制数的字符串：%o", 255);
		System.out.println("fromOct=" + fromOct);
		
		String fromHex = String.format("格式化八进制数的字符串：%x", 255);
		System.out.println("fromHex=" + fromHex);
		
		String fromFloat = String.format("格式化浮点数的字符串：%f", 3.14);
		System.out.println("fromFloat=" + fromFloat);
		
		String manyVariable = String.format(
				"以下字符串包括了多个变量值：%s，%c，%b，%d，%o，%x，%f", "Hello", 'A', false, 255,
				255, 255, 3.14);
		System.out.println("manyVariable=" + manyVariable);

	
		String fromDouble = String.format("双精度数格式化后丢失精度的字符串：%f", 3.1415926);
		System.out.println("fromDouble=" + fromDouble);
		
		String fromDecimal = String.format("格式化双精度数的字符串：%.8f", 3.1415926);
		System.out.println("fromDecimal=" + fromDecimal);
	
		String fromLenth = String.format("格式化固定长度（默认右对齐）的整数字符串：(%8d)", 255);
		System.out.println("fromLenth=" + fromLenth);
	
		String fromLeft = String.format("格式化固定长度且左对齐的整数字符串：(%-8d)", 255);
		System.out.println("fromLeft=" + fromLeft);
	
		String fromZero = String.format("格式化固定长度且左补0的整数字符串：(%08d)", 255);
		System.out.println("fromZero=" + fromZero);

		
		String fromRepeat1 = String.format("重要的事情说三遍：%s，%s，%s", "别迟到", "别迟到",
				"别迟到");
		System.out.println("fromRepeat1=" + fromRepeat1);
		
		String fromRepeat2 = String.format("重要的事情说三遍：%1$s，%1$s，%1$s", "别迟到");
		System.out.println("fromRepeat2=" + fromRepeat2);

		double normalDecimal = 19.895;
		
		String normalResult = formatWithDouble(normalDecimal, 2);
		System.out.println("normalResult=" + normalResult);
		BigDecimal bigDecimal = new BigDecimal("123456789012345678.901");
		
		String bigResult = formatWithBigDecimal(bigDecimal, 2);
		System.out.println("bigResult=" + bigResult);
	}

	
	public static String formatWithDouble(double value, int digit) {
		
		String format = String.format("%%.%df", digit);
		
		String result = String.format(format, value);
		return result;
	}

	
	public static String formatWithBigDecimal(BigDecimal value, int digit) {
		
		BigDecimal result = value.setScale(digit, RoundingMode.HALF_UP);
		return result.toString();
	}

}


```
```
//5.8
package com.string.string;


public class StrMethod {

	public static void main(String[] arg) {
		String hello = "Hello World. 你好世界。";
		boolean isEmpty = hello.isEmpty(); 
		System.out.println("是否为空 = " + isEmpty);
		boolean equals = hello.equals("你好"); 
		System.out.println("是否等于你好 = " + equals);
		boolean startsWith = hello.startsWith("Hello"); 
		System.out.println("是否以Hello开头 = " + startsWith);
		boolean endsWith = hello.endsWith("World"); 
		System.out.println("是否以World结尾 = " + endsWith);
		boolean contains = hello.contains("or"); 
		System.out.println("是否包含or = " + contains);

		int char_length = hello.length(); 
		System.out.println("字符数 = " + char_length);
		int byte_length = hello.getBytes().length;
		System.out.println("字节数 = " + byte_length);
		char first = hello.charAt(0);
		System.out.println("首字符 = " + first);
		int index = hello.indexOf("l");
		System.out.println("首次找到l的位置 = " + index);
		int lastIndex = hello.lastIndexOf("l");
		System.out.println("最后找到l的位置 = " + lastIndex);
		
		String lowerCase = hello.toLowerCase(); 
		System.out.println("转换为小写字母 = " + lowerCase);
		String upperCase = hello.toUpperCase(); 
		System.out.println("转换为大写字母 = " + upperCase);
		String trim = hello.trim(); 
		System.out.println("去掉首尾空格 = " + trim);
		String concat = hello.concat("Fine, thank you."); 
		System.out.println("追加了目标串 = " + concat);
		
		String subToEnd = hello.substring(6);
		System.out.println("从第六位截取到末尾 = " + subToEnd);
		
		String subToCustom = hello.substring(6, 9);
		System.out.println("从第六位截取到第九位 = " + subToCustom);
		String replace = hello.replace("l", "L"); 
		System.out.println("把l替换为L = " + replace);
	}

}


```
```
//5.9
package com.string;


public class IcnoExtract {

	public static void main(String[] arg) {
		String[] icnoArray = new String[]{
				"110108208802290199", "11011420880903294x", "110101208806180030"
		};
		for (String icno : icnoArray) {
			String result = extractIc(icno);
			System.out.println(String.format("%s的校验结果为：%s", icno, result));
		}
	}

	
	private static String extractIc(String icno) {
		if (!isICNO(icno)) { 
			return "该身份证的号码不合法";
		}
		if (!isValidIc(icno)) { 
			return "该身份证的最后一位计算有误";
		}

		String[] areaIds = { "110101", "110102", "110105", "110106", 
				"110107", "110108", "110109", "110111", "110112", "110113", 
				"110114", "110115", "110116", "110117", "110118", "110119" };
		
		String[] areaNames = { "东城区", "西城区", "朝阳区", "丰台区", 
				"石景山区", "海淀区", "门头沟区", "房山区", "通州区", "顺义区", 
				"昌平区", "大兴区", "怀柔区", "平谷区", "密云区", "延庆区" };
		String icPrefix = icno.substring(0, 6); 
		String icArea = "";
		for (int i = 0; i < areaIds.length; i++) { 
			if (icPrefix.equals(areaIds[i])) {
				icArea = "北京市" + areaNames[i];
				break;
			}
		}
		if (icArea.isEmpty()) { 
			return "该身份证不是北京号码";
		}
		
		String birthday = String.format("%s年%s月%s日", icno.substring(6, 10),
				icno.substring(10, 12), icno.substring(12, 14));
		String seqNro = icno.substring(14, 17); 
		int sexSign = Integer.parseInt(icno.substring(16, 17));
		
		String sexName = (sexSign % 2 == 1) ? "男" : "女";
		return String.format("居住地址是%s，出生日期是%s，出生序号是%s，性别是%s。",
					icArea, birthday, seqNro, sexName);
	}

	
	public static boolean isICNO(String icno) {
		String regex = "((1[1-5]|2[1-3]|3[1-7]|4[1-6]|5[0-4]|6[1-5]|8[1-3])\\d{4})((19|20)\\d{2})(0[1-9]|1[0-2])(0[1-9]|[12]\\d|3[01])(\\d{3}([0-9xX]))";
		return icno.matches(regex);
	}

	
	public static void checkArea() {
		String regex = "(1[1-5]|2[1-3]|3[1-7]|4[1-6]|5[0-4]|6[1-5]|8[1-3])\\d{4}";
		for (int i = 0; i <= 90; i++) {
			String area = String.format("%06d", i * 10000);
			boolean check = area.matches(regex);
			System.out.println("area = " + area + ", check = " + check);
		}
	}

	
	public static boolean isValidIc(String icno) {
	
		int[] factors = { 7, 9, 10, 5, 8, 4, 2, 1, 6, 3, 7, 9, 10, 5, 8, 4, 2 };
		int sum = 0; 
		for (int i = 0; i < 17; i++) {
			
			int perNum = icno.charAt(i) - '0';
			sum += perNum * factors[i];
		}
		int remainder = sum % 11; 
		
		char[] lastChars = { '1', '0', 'X', '9', '8', '7', '6', '5', '4', '3', '2' };
		char lastChar = lastChars[remainder]; 
		
		char realLastChar = Character.toUpperCase(icno.charAt(17));
		
		if (lastChar == realLastChar) { 
			return true;
		} else { 
			return false;
		}
	}

}


```
```
//5.10
package com.string;

import java.util.Arrays;


public class KmpSearch {

	public static void main(String[] arg) {
		String src_cn = "吃葡萄不吐葡萄皮，不吃葡萄倒吐葡萄皮。";
		String dest_cn = "葡萄";
		int[] posArray = findString(src_cn, dest_cn);
		for (int pos : posArray) {
			System.out.println("pos = " + pos);
		}
		String src_en = "BBBBBBABCVVVABCDEABCFABCDEYYYYYYABCDEYYYYYABCDEABCFABCDEGGG";
		String dest_en = "ABCDEABCFABCDE";
		
		int[] posArrayByBF = findStringByBF(src_en, dest_en);
		for (int pos : posArrayByBF) {
			System.out.println("pos by BF = " + pos);
		}
		
		int[] posArrayByKMP = findStringByKMP(src_en, dest_en);
		for (int pos : posArrayByKMP) {
			System.out.println("pos by KMP = " + pos);
		}
	}

	
	private static int[] findString(String src, String dest) {
		int[] posArray = new int[0]; 
		int pos = 0; 
		for (int count = 1; pos >= 0; count++) {
			pos = src.indexOf(dest, pos); 
			if (pos < 0) { 
				break;
			}
			posArray = Arrays.copyOf(posArray, count); 
			posArray[count - 1] = pos;
			pos += dest.length(); 
		}
		return posArray;
	}

	private static int[] findStringByBF(String src, String dest) {
		int total_count = 0;
		char[] srcArray = src.toCharArray(); 
		char[] destArray = dest.toCharArray(); 
		int[] posArray = new int[0]; 
		int count = 0; 
		
		loop: for (int i = 0; i < srcArray.length; i++, total_count++) {
			for (int j = 0; j < destArray.length; j++, total_count++) {
				if (srcArray[i + j] != destArray[j]) {
					continue loop; 
				} else if (j == destArray.length - 1) { 
					count++;
					posArray = Arrays.copyOf(posArray, count); 
					posArray[count - 1] = i; 
				}
			}
		}
		System.out.println("BF算法的总比较次数 = " + total_count);
		return posArray;
	}

	
	private static int[] findStringByKMP(String src, String dest) {
		int total_count = 0;
		char[] srcArray = src.toCharArray(); 
		char[] destArray = dest.toCharArray(); 
		
		int[] matchArray = new int[destArray.length];
		Arrays.fill(matchArray, 0);
		
		for (int i = 0; i < destArray.length; i++) {
			for (int j = i + 1; j < destArray.length; j++, total_count++) {
				if (destArray[i] == destArray[j]) {
					matchArray[j] = matchArray[j - 1] + 1;
				}
			}
		}
		for (int match : matchArray) {
			System.out.print(match+" ");
		}
		System.out.println();
		System.out.println("KMP算法的关键词比较次数 = " + total_count);
		
		int[] posArray = new int[0];
		int count = 0; 
		loop: for (int i = 0; i < srcArray.length; i++, total_count++) {
			for (int j = 0; j < destArray.length; j++, total_count++) {
				if (srcArray[i + j] != destArray[j]) { 
					if (j > 0) {
						i--;
						i = i + j - matchArray[j];
					}
					continue loop;
				} else if (j == destArray.length - 1) {
					count++;
					posArray = Arrays.copyOf(posArray, count); 
					posArray[count - 1] = i;
				}
			}
		}
		System.out.println("KMP算法的总比较次数 = " + total_count);
		return posArray;
	}
}

```
```
//5.11
package com.string;


public class ParseAddress {

	public static void main(String[] arg) {
		String[] infoArray = new String[]{
				"张三 11900000000 北京市海淀区双清路30号",
				"059100000000,福建省福州市闽侯县上街镇工贸路3号,李四",
				"11900000000 王五 四川省凉山彝族自治州西昌市大水井12号",
				"西藏自治区阿里地区噶尔县狮泉河镇迎宾大道26号,赵六,059100000000",
				"刘七 内蒙古自治区阿拉善盟额济纳旗达来呼布镇黑水城遗址 11900000000"
		};
		for (String info : infoArray) { 
			parseReceiverInfo(info); 
		}
	}
	
	
	private static void parseReceiverInfo(String info) {
		String[] splits = info.split(" |,"); 
		String name="", phone="", address="";
		for (String str : splits) {
			if (isPhone(str)) {
				phone = str;
			} else if (name.equals("")) {
				name = str;
			} else if (str.length() > name.length()) { 
				address = str;
			} else { 
				address = name;
				name = str;
			}
		}
		System.out.println(String.format("姓名：%s, 电话：%s, 收件地址：%s", name, phone, address));

		
		String[] areaArray = new String[]{"", address};
		
		areaArray = getAreaName(areaArray[1], new String[]{"省", "自治区"});
		String province = areaArray[0]; 
		
		areaArray = getAreaName(areaArray[1], new String[]{"自治州", "地区", "盟", "市"});
		String city = areaArray[0]; 
		
		areaArray = getAreaName(areaArray[1], new String[]{"县", "市", "区", "旗"});
		String district = areaArray[0]; 
		String detail = areaArray[1]; 
		if (province.length() <= 0) { 
			province = city;
		}
		System.out.println(String.format("省份：%s, 地市：%s, 区县：%s, 详细地址：%s", 
				province, city, district, detail));
	}
	
	private static boolean isPhone(String phone) {	
		String regex = "\\d+";		
		return phone.matches(regex);
	}

	
	private static String[] getAreaName(String address, String[] suffixArray) {
		
		String[] areaArray = new String[]{"", address};
		int pos = 0;
		for (String suffix : suffixArray) {
			pos = address.indexOf(suffix); 
			if (pos > 0) { 
				
				areaArray[0] = address.substring(0, pos+suffix.length());
				
				areaArray[1] = address.substring(pos+suffix.length());
				break; 
			}
		}
		return areaArray;
	}

}
```


```
