---
title: 数学関数
ms.date: 01/27/2020
helpviewer_keywords:
- math functions, Visual Basic
- arithmetic operations, math functions
- math routines
- Atn function
ms.assetid: 4d2d82e7-6924-42fe-a4a7-b4dd5bebbd0c
ms.openlocfilehash: ea30ae3b30484c1a13d6d540f121c03afb30ba26
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794592"
---
# <a name="math-functions-visual-basic"></a><span data-ttu-id="6d24f-102">数値演算関数 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6d24f-102">Math Functions (Visual Basic)</span></span>

<span data-ttu-id="6d24f-103"><xref:System.Math?displayProperty=nameWithType> クラスのメソッドは、三角関数や対数関数などの一般的な数値関数を提供します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-103">The methods of the <xref:System.Math?displayProperty=nameWithType> class provide trigonometric, logarithmic, and other common mathematical functions.</span></span>

## <a name="remarks"></a><span data-ttu-id="6d24f-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="6d24f-104">Remarks</span></span>

<span data-ttu-id="6d24f-105"><xref:System.Math?displayProperty=nameWithType> クラスのメソッドを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-105">The following table lists methods of the <xref:System.Math?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="6d24f-106">Visual Basic プログラムで使用できるものは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6d24f-106">You can use these in a Visual Basic program:</span></span>
  
|<span data-ttu-id="6d24f-107">.NET メソッド</span><span class="sxs-lookup"><span data-stu-id="6d24f-107">.NET method</span></span>|<span data-ttu-id="6d24f-108">説明</span><span class="sxs-lookup"><span data-stu-id="6d24f-108">Description</span></span>|
|---------------------------|-----------------|
|<xref:System.Math.Abs%2A>|<span data-ttu-id="6d24f-109">絶対値を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-109">Returns the absolute value of a number.</span></span>|
|<xref:System.Math.Acos%2A>|<span data-ttu-id="6d24f-110">コサインが指定数となる角度を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-110">Returns the angle whose cosine is the specified number.</span></span>|
|<xref:System.Math.Asin%2A>|<span data-ttu-id="6d24f-111">サインが指定数となる角度を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-111">Returns the angle whose sine is the specified number.</span></span>|
|<xref:System.Math.Atan%2A>|<span data-ttu-id="6d24f-112">タンジェントが指定数となる角度を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-112">Returns the angle whose tangent is the specified number.</span></span>|
|<xref:System.Math.Atan2%2A>|<span data-ttu-id="6d24f-113">タンジェントが 2 つの指定された数の商である角度を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-113">Returns the angle whose tangent is the quotient of two specified numbers.</span></span>|
|<xref:System.Math.BigMul%2A>|<span data-ttu-id="6d24f-114">2 つの 32 ビット数値の完全な積を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-114">Returns the full product of two 32-bit numbers.</span></span>|
|<xref:System.Math.Ceiling%2A>|<span data-ttu-id="6d24f-115">指定した `Decimal` または `Double` 以上の数のうち、最小の整数値を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-115">Returns the smallest integral value that's greater than or equal to the specified `Decimal` or `Double`.</span></span>|
|<xref:System.Math.Cos%2A>|<span data-ttu-id="6d24f-116">指定された角度のコサインを返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-116">Returns the cosine of the specified angle.</span></span>|
|<xref:System.Math.Cosh%2A>|<span data-ttu-id="6d24f-117">指定された角度のハイパーボリック コサインを返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-117">Returns the hyperbolic cosine of the specified angle.</span></span>|
|<xref:System.Math.DivRem%2A>|<span data-ttu-id="6d24f-118">2 つの 32 ビットまたは 64 ビットの符号付き整数の商を返し、出力パラメーターの剰余を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-118">Returns the quotient of two 32-bit or 64-bit signed integers, and also returns the remainder in an output parameter.</span></span>|
|<xref:System.Math.Exp%2A>|<span data-ttu-id="6d24f-119">e (自然対数の底) を指定した回数だけべき乗して返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-119">Returns e (the base of natural logarithms) raised to the specified power.</span></span>|
|<xref:System.Math.Floor%2A>|<span data-ttu-id="6d24f-120">指定した `Decimal` または `Double` の数値以下の最大の整数を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-120">Returns the largest integer that's less than or equal to the specified `Decimal` or `Double` number.</span></span>|
|<xref:System.Math.IEEERemainder%2A>|<span data-ttu-id="6d24f-121">指定した数を指定した別の数で除算した結果の剰余を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-121">Returns the remainder that results from the division of a specified number by another specified number.</span></span>|
|<xref:System.Math.Log%2A>|<span data-ttu-id="6d24f-122">指定した数値の自然対数 (底 e) または指定した数値の指定した底での対数を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-122">Returns the natural (base e) logarithm of a specified number or the logarithm of a specified number in a specified base.</span></span>|
|<xref:System.Math.Log10%2A>|<span data-ttu-id="6d24f-123">指定した数の底 10 の対数を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-123">Returns the base 10 logarithm of a specified number.</span></span>|
|<xref:System.Math.Max%2A>|<span data-ttu-id="6d24f-124">2 つの数値の大きい方を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-124">Returns the larger of two numbers.</span></span>|
|<xref:System.Math.Min%2A>|<span data-ttu-id="6d24f-125">2 つの数のうち、小さい方を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-125">Returns the smaller of two numbers.</span></span>|
|<xref:System.Math.Pow%2A>|<span data-ttu-id="6d24f-126">指定の数値を指定した値で累乗した値を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-126">Returns a specified number raised to the specified power.</span></span>|
|<xref:System.Math.Round%2A>|<span data-ttu-id="6d24f-127">`Decimal` または `Double` の値を、最も近い整数値または指定した小数点以下の桁数に丸めます。</span><span class="sxs-lookup"><span data-stu-id="6d24f-127">Returns a `Decimal` or `Double` value rounded to the nearest integral value or to a specified number of fractional digits.</span></span>|
|<xref:System.Math.Sign%2A>|<span data-ttu-id="6d24f-128">数値の符号を示す `Integer` 値を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-128">Returns an `Integer` value indicating the sign of a number.</span></span>|
|<xref:System.Math.Sin%2A>|<span data-ttu-id="6d24f-129">指定された角度のサインを返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-129">Returns the sine of the specified angle.</span></span>|
|<xref:System.Math.Sinh%2A>|<span data-ttu-id="6d24f-130">指定された角度のハイパーボリック サインを返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-130">Returns the hyperbolic sine of the specified angle.</span></span>|
|<xref:System.Math.Sqrt%2A>|<span data-ttu-id="6d24f-131">指定された数値の平方根を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-131">Returns the square root of a specified number.</span></span>|
|<xref:System.Math.Tan%2A>|<span data-ttu-id="6d24f-132">指定された角度のタンジェントを返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-132">Returns the tangent of the specified angle.</span></span>|
|<xref:System.Math.Tanh%2A>|<span data-ttu-id="6d24f-133">指定された角度のハイパーボリック タンジェントを返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-133">Returns the hyperbolic tangent of the specified angle.</span></span>|
|<xref:System.Math.Truncate%2A>|<span data-ttu-id="6d24f-134">指定した `Decimal` または `Double` の数値の整数部を計算します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-134">Calculates the integral part of a specified `Decimal` or `Double` number.</span></span>|

<span data-ttu-id="6d24f-135">次の表に、.NET Framework には存在しないが .NET Standard または .NET Core に追加される <xref:System.Math?displayProperty=nameWithType> クラスのメソッドを示します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-135">The following table lists methods of the <xref:System.Math?displayProperty=nameWithType> class that don't exist in .NET Framework but are added in .NET Standard or .NET Core:</span></span>

|<span data-ttu-id="6d24f-136">.NET メソッド</span><span class="sxs-lookup"><span data-stu-id="6d24f-136">.NET method</span></span>|<span data-ttu-id="6d24f-137">説明</span><span class="sxs-lookup"><span data-stu-id="6d24f-137">Description</span></span>|<span data-ttu-id="6d24f-138">利用可能</span><span class="sxs-lookup"><span data-stu-id="6d24f-138">Available in</span></span>|
|---------------------------|-----------------|-----------|
|<xref:System.Math.Acosh%2A>|<span data-ttu-id="6d24f-139">ハイパーボリック コサインが指定数となる角度を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-139">Returns the angle whose hyperbolic cosine is the specified number.</span></span>|<span data-ttu-id="6d24f-140">.NET Core 2.1 および .NET Standard 2.1 以降</span><span class="sxs-lookup"><span data-stu-id="6d24f-140">Starting with .NET Core 2.1 and .NET Standard 2.1</span></span>|
|<xref:System.Math.Asinh%2A>|<span data-ttu-id="6d24f-141">ハイパーボリック サインが指定数となる角度を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-141">Returns the angle whose hyperbolic sine is the specified number.</span></span>|<span data-ttu-id="6d24f-142">.NET Core 2.1 および .NET Standard 2.1 以降</span><span class="sxs-lookup"><span data-stu-id="6d24f-142">Starting with .NET Core 2.1 and .NET Standard 2.1</span></span>|
|<xref:System.Math.Atanh%2A>|<span data-ttu-id="6d24f-143">ハイパーボリック タンジェントが指定数となる角度を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-143">Returns the angle whose hyperbolic tangent is the specified number.</span></span>|<span data-ttu-id="6d24f-144">.NET Core 2.1 および .NET Standard 2.1 以降</span><span class="sxs-lookup"><span data-stu-id="6d24f-144">Starting with .NET Core 2.1 and .NET Standard 2.1</span></span>|
|<xref:System.Math.BitDecrement%2A>|<span data-ttu-id="6d24f-145">`x` 未満を比較する、次に小さい値を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-145">Returns the next smallest value that compares less than `x`.</span></span>|<span data-ttu-id="6d24f-146">.NET Core 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="6d24f-146">Starting with .NET Core 3.0</span></span>|
|<xref:System.Math.BitIncrement%2A>|<span data-ttu-id="6d24f-147">`x` を超える比較値の次に大きい値を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-147">Returns the next largest value that compares greater than `x`.</span></span>|<span data-ttu-id="6d24f-148">.NET Core 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="6d24f-148">Starting with .NET Core 3.0</span></span>|
|<xref:System.Math.Cbrt%2A>|<span data-ttu-id="6d24f-149">指定された数値の立方根を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-149">Returns the cube root of a specified number.</span></span>|<span data-ttu-id="6d24f-150">.NET Core 2.1 および .NET Standard 2.1 以降</span><span class="sxs-lookup"><span data-stu-id="6d24f-150">Starting with .NET Core 2.1 and .NET Standard 2.1</span></span>|
|<xref:System.Math.Clamp%2A>|<span data-ttu-id="6d24f-151">`min` 以上 `max` 以下の範囲に固定される `value` を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-151">Returns `value` clamped to the inclusive range of `min` and `max`.</span></span>|<span data-ttu-id="6d24f-152">.NET Core 2.0 および .NET Standard 2.1 以降</span><span class="sxs-lookup"><span data-stu-id="6d24f-152">Starting with .NET Core 2.0 and .NET Standard 2.1</span></span>|
|<xref:System.Math.CopySign%2A>|<span data-ttu-id="6d24f-153">`x` の絶対値と符号 `y` の値を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-153">Returns a value with the magnitude of `x` and the sign of `y`.</span></span>|<span data-ttu-id="6d24f-154">.NET Core 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="6d24f-154">Starting with .NET Core 3.0</span></span>|
|<xref:System.Math.FusedMultiplyAdd%2A>|<span data-ttu-id="6d24f-155">1 つの三項演算として丸められた、(x \* y) + z を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-155">Returns (x \* y) + z, rounded as one ternary operation.</span></span>|<span data-ttu-id="6d24f-156">.NET Core 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="6d24f-156">Starting with .NET Core 3.0</span></span>|
|<xref:System.Math.ILogB%2A>|<span data-ttu-id="6d24f-157">指定した数の底 2 の整数の対数を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-157">Returns the base 2 integer logarithm of a specified number.</span></span>|<span data-ttu-id="6d24f-158">.NET Core 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="6d24f-158">Starting with .NET Core 3.0</span></span>|
|<xref:System.Math.Log2%2A>|<span data-ttu-id="6d24f-159">指定した数の底 2 の対数を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-159">Returns the base 2 logarithm of a specified number.</span></span>|<span data-ttu-id="6d24f-160">.NET Core 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="6d24f-160">Starting with .NET Core 3.0</span></span>|
|<xref:System.Math.MaxMagnitude%2A>|<span data-ttu-id="6d24f-161">2 つの倍精度浮動小数点数のうち、大きい絶対値を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-161">Returns the larger magnitude of two double-precision floating-point numbers.</span></span>|<span data-ttu-id="6d24f-162">.NET Core 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="6d24f-162">Starting with .NET Core 3.0</span></span>|
|<xref:System.Math.MinMagnitude%2A>|<span data-ttu-id="6d24f-163">2 つの倍精度浮動小数点数のうち、小さい絶対値を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-163">Returns the smaller magnitude of two double-precision floating-point numbers.</span></span>|<span data-ttu-id="6d24f-164">.NET Core 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="6d24f-164">Starting with .NET Core 3.0</span></span>|
|<xref:System.Math.ScaleB%2A>|<span data-ttu-id="6d24f-165">効率的に計算された x \* 2^n を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-165">Returns x \* 2^n computed efficiently.</span></span>|<span data-ttu-id="6d24f-166">.NET Core 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="6d24f-166">Starting with .NET Core 3.0</span></span>|

<span data-ttu-id="6d24f-167">これらの関数を修飾なしで使用するには、ソース ファイルの先頭に次のコードを追加して、<xref:System.Math?displayProperty=nameWithType> 名前空間をプロジェクトにインポートします。</span><span class="sxs-lookup"><span data-stu-id="6d24f-167">To use these functions without qualification, import the <xref:System.Math?displayProperty=nameWithType> namespace into your project by adding the following code to the top of your source file:</span></span>

```vb
Imports System.Math
```

## <a name="example---abs"></a><span data-ttu-id="6d24f-168">例 - Abs</span><span class="sxs-lookup"><span data-stu-id="6d24f-168">Example - Abs</span></span>

<span data-ttu-id="6d24f-169">この例では、<xref:System.Math> クラスの <xref:System.Math.Abs%2A> メソッドを使用して数値の絶対値を計算します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-169">This example uses the <xref:System.Math.Abs%2A> method of the <xref:System.Math> class to compute the absolute value of a number.</span></span>

```vb
Dim x As Double = Math.Abs(50.3)
Dim y As Double = Math.Abs(-50.3)
Console.WriteLine(x)
Console.WriteLine(y)
' This example produces the following output:
' 50.3
' 50.3
```  

## <a name="example---atan"></a><span data-ttu-id="6d24f-170">例 - Atan</span><span class="sxs-lookup"><span data-stu-id="6d24f-170">Example - Atan</span></span>

<span data-ttu-id="6d24f-171">この例では、<xref:System.Math> クラスの <xref:System.Math.Atan%2A> メソッドを使用して pi の値を計算します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-171">This example uses the <xref:System.Math.Atan%2A> method of the <xref:System.Math> class to calculate the value of pi.</span></span>

```vb
Public Function GetPi() As Double
    ' Calculate the value of pi.
    Return 4.0 * Math.Atan(1.0)
End Function
```

> [!NOTE]
> <span data-ttu-id="6d24f-172"><xref:System.Math?displayProperty=nameWithType> クラスには <xref:System.Math.PI?displayProperty=nameWithType> 定数フィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6d24f-172">The <xref:System.Math?displayProperty=nameWithType> class contains <xref:System.Math.PI?displayProperty=nameWithType> constant field.</span></span> <span data-ttu-id="6d24f-173">それを計算するのではなく、使用することができます。</span><span class="sxs-lookup"><span data-stu-id="6d24f-173">You can use it rather than calculating it.</span></span>

## <a name="example---cos"></a><span data-ttu-id="6d24f-174">例 - Cos</span><span class="sxs-lookup"><span data-stu-id="6d24f-174">Example - Cos</span></span>

<span data-ttu-id="6d24f-175">この例では、<xref:System.Math> クラスの <xref:System.Math.Cos%2A> メソッドを使用して角度のコサインを返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-175">This example uses the <xref:System.Math.Cos%2A> method of the <xref:System.Math> class to return the cosine of an angle.</span></span>

```vb
Public Function Sec(angle As Double) As Double
    ' Calculate the secant of angle, in radians.
    Return 1.0 / Math.Cos(angle)
End Function
```

## <a name="example---exp"></a><span data-ttu-id="6d24f-176">例 - Exp</span><span class="sxs-lookup"><span data-stu-id="6d24f-176">Example - Exp</span></span>

<span data-ttu-id="6d24f-177">この例では、<xref:System.Math> クラスの <xref:System.Math.Exp%2A> メソッドを使用して e の累乗値を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-177">This example uses the <xref:System.Math.Exp%2A> method of the <xref:System.Math> class to return e raised to a power.</span></span>

```vb
Public Function Sinh(angle As Double) As Double
    ' Calculate hyperbolic sine of an angle, in radians.
    Return (Math.Exp(angle) - Math.Exp(-angle)) / 2.0
End Function
```

## <a name="example---log"></a><span data-ttu-id="6d24f-178">例 - Log</span><span class="sxs-lookup"><span data-stu-id="6d24f-178">Example - Log</span></span>

<span data-ttu-id="6d24f-179">この例では、<xref:System.Math> クラスの <xref:System.Math.Log%2A> メソッドを使用して数値の自然対数を返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-179">This example uses the <xref:System.Math.Log%2A> method of the <xref:System.Math> class to return the natural logarithm of a number.</span></span>

```vb
Public Function Asinh(value As Double) As Double
    ' Calculate inverse hyperbolic sine, in radians.
    Return Math.Log(value + Math.Sqrt(value * value + 1.0))
End Function
```

## <a name="example---round"></a><span data-ttu-id="6d24f-180">例 - Round</span><span class="sxs-lookup"><span data-stu-id="6d24f-180">Example - Round</span></span>

<span data-ttu-id="6d24f-181">この例では、<xref:System.Math> クラスの <xref:System.Math.Round%2A> メソッドを使用して数値を最も近い整数に丸めます。</span><span class="sxs-lookup"><span data-stu-id="6d24f-181">This example uses the <xref:System.Math.Round%2A> method of the <xref:System.Math> class to round a number to the nearest integer.</span></span>

```vb
Dim myVar2 As Double = Math.Round(2.8)
Console.WriteLine(myVar2)
' The code produces the following output:
' 3
```

## <a name="example---sign"></a><span data-ttu-id="6d24f-182">例 - Sign</span><span class="sxs-lookup"><span data-stu-id="6d24f-182">Example - Sign</span></span>

<span data-ttu-id="6d24f-183">この例では、<xref:System.Math> クラスの <xref:System.Math.Sign%2A> メソッドを使用して数値の符号を調べます。</span><span class="sxs-lookup"><span data-stu-id="6d24f-183">This example uses the <xref:System.Math.Sign%2A> method of the <xref:System.Math> class to determine the sign of a number.</span></span>

```vb
Dim mySign1 As Integer = Math.Sign(12)
Dim mySign2 As Integer = Math.Sign(-2.4)
Dim mySign3 As Integer = Math.Sign(0)
Console.WriteLine(mySign1)
Console.WriteLine(mySign2)
Console.WriteLine(mySign3)
' The code produces the following output:
' 1
' -1
' 0
```

## <a name="example---sin"></a><span data-ttu-id="6d24f-184">例 - Sin</span><span class="sxs-lookup"><span data-stu-id="6d24f-184">Example - Sin</span></span>

<span data-ttu-id="6d24f-185">この例では、<xref:System.Math> クラスの <xref:System.Math.Sin%2A> メソッドを使用して角度のサインを返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-185">This example uses the <xref:System.Math.Sin%2A> method of the <xref:System.Math> class to return the sine of an angle.</span></span>

```vb
Public Function Csc(angle As Double) As Double
    ' Calculate cosecant of an angle, in radians.
    Return 1.0 / Math.Sin(angle)
End Function
```

## <a name="example---sqrt"></a><span data-ttu-id="6d24f-186">例 - Sqrt</span><span class="sxs-lookup"><span data-stu-id="6d24f-186">Example - Sqrt</span></span>

<span data-ttu-id="6d24f-187">この例では、<xref:System.Math> クラスの <xref:System.Math.Sqrt%2A> メソッドを使用して数値の平方根を計算します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-187">This example uses the <xref:System.Math.Sqrt%2A> method of the <xref:System.Math> class to calculate the square root of a number.</span></span>

```vb
Dim mySqrt1 As Double = Math.Sqrt(4)
Dim mySqrt2 As Double = Math.Sqrt(23)
Dim mySqrt3 As Double = Math.Sqrt(0)
Dim mySqrt4 As Double = Math.Sqrt(-4)
Console.WriteLine(mySqrt1)
Console.WriteLine(mySqrt2)
Console.WriteLine(mySqrt3)
Console.WriteLine(mySqrt4)
' The code produces the following output:
' 2
' 4.79583152331272
' 0
' NaN
```

## <a name="example---tan"></a><span data-ttu-id="6d24f-188">例 - Tan</span><span class="sxs-lookup"><span data-stu-id="6d24f-188">Example - Tan</span></span>

<span data-ttu-id="6d24f-189">この例では、<xref:System.Math> クラスの <xref:System.Math.Tan%2A> メソッドを使用して角度のタンジェントを返します。</span><span class="sxs-lookup"><span data-stu-id="6d24f-189">This example uses the <xref:System.Math.Tan%2A> method of the <xref:System.Math> class to return the tangent of an angle.</span></span>

```vb
Public Function Ctan(angle As Double) As Double
    ' Calculate cotangent of an angle, in radians.
    Return 1.0 / Math.Tan(angle)
End Function
```

## <a name="see-also"></a><span data-ttu-id="6d24f-190">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d24f-190">See also</span></span>

- <xref:Microsoft.VisualBasic.VBMath.Rnd%2A>
- <xref:Microsoft.VisualBasic.VBMath.Randomize%2A>
- <xref:System.Double.NaN>
- [<span data-ttu-id="6d24f-191">数値演算関数の導出</span><span class="sxs-lookup"><span data-stu-id="6d24f-191">Derived Math Functions</span></span>](../keywords/derived-math-functions.md)
- [<span data-ttu-id="6d24f-192">算術演算子</span><span class="sxs-lookup"><span data-stu-id="6d24f-192">Arithmetic Operators</span></span>](../operators/arithmetic-operators.md)
