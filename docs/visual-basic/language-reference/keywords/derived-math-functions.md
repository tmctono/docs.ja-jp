---
title: 数値演算関数の導出
ms.date: 07/20/2015
helpviewer_keywords:
- arithmetic operations, derived math functions
- cosecant function
- arcsecant function
- arccotangent function
- functions [Visual Basic], derived math functions
- inverse functions
- math functions, derived
- derived math functions
- cotangent function
- angles
- secant function
- trigonometric functions
- logarithms
- arccosecant function
- hyperbolic functions
- arcsine function
- degrees
- arccosine function
ms.assetid: 63e449d8-9444-44fb-8db1-6d9cf346e2aa
ms.openlocfilehash: 73cf56dd72f2baac0474d6f5c4e88228a1fe38cf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349848"
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="13b00-102">数値演算関数の導出 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="13b00-102">Derived Math Functions (Visual Basic)</span></span>
<span data-ttu-id="13b00-103">次の表に、<xref:System.Math?displayProperty=nameWithType> オブジェクトの組み込み数学関数から導出できる非組み込み数学関数を示します。</span><span class="sxs-lookup"><span data-stu-id="13b00-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="13b00-104">組み込み数学関数にアクセスするには、ファイルまたはプロジェクトに `Imports System.Math` を追加します。</span><span class="sxs-lookup"><span data-stu-id="13b00-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="13b00-105">関数</span><span class="sxs-lookup"><span data-stu-id="13b00-105">Function</span></span>|<span data-ttu-id="13b00-106">導出した同等物</span><span class="sxs-lookup"><span data-stu-id="13b00-106">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="13b00-107">Secant (Sec(x))</span><span class="sxs-lookup"><span data-stu-id="13b00-107">Secant (Sec(x))</span></span>|<span data-ttu-id="13b00-108">1 / Cos(x)</span><span class="sxs-lookup"><span data-stu-id="13b00-108">1 / Cos(x)</span></span>|  
|<span data-ttu-id="13b00-109">Cosecant (Csc(x))</span><span class="sxs-lookup"><span data-stu-id="13b00-109">Cosecant (Csc(x))</span></span>|<span data-ttu-id="13b00-110">1 / Sin(x)</span><span class="sxs-lookup"><span data-stu-id="13b00-110">1 / Sin(x)</span></span>|  
|<span data-ttu-id="13b00-111">Cotangent (Ctan(x))</span><span class="sxs-lookup"><span data-stu-id="13b00-111">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="13b00-112">1 / Tan(x)</span><span class="sxs-lookup"><span data-stu-id="13b00-112">1 / Tan(x)</span></span>|  
|<span data-ttu-id="13b00-113">Inverse sine (Asin(x))</span><span class="sxs-lookup"><span data-stu-id="13b00-113">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="13b00-114">Atan(x / Sqrt(-x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="13b00-114">Atan(x / Sqrt(-x \* x + 1))</span></span>|  
|<span data-ttu-id="13b00-115">Inverse cosine (Acos(x))</span><span class="sxs-lookup"><span data-stu-id="13b00-115">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="13b00-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span><span class="sxs-lookup"><span data-stu-id="13b00-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="13b00-117">Inverse secant (Asec(x))</span><span class="sxs-lookup"><span data-stu-id="13b00-117">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="13b00-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="13b00-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="13b00-119">Inverse cosecant (Acsc(x))</span><span class="sxs-lookup"><span data-stu-id="13b00-119">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="13b00-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="13b00-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="13b00-121">Inverse cotangent (Acot(x))</span><span class="sxs-lookup"><span data-stu-id="13b00-121">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="13b00-122">2 \* Atan(1) - Atan(x)</span><span class="sxs-lookup"><span data-stu-id="13b00-122">2 \* Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="13b00-123">Hyperbolic sine (Sinh(x))</span><span class="sxs-lookup"><span data-stu-id="13b00-123">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="13b00-124">(Exp(x) – Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="13b00-124">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="13b00-125">Hyperbolic cosine (Cosh(x))</span><span class="sxs-lookup"><span data-stu-id="13b00-125">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="13b00-126">(Exp(x) + Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="13b00-126">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="13b00-127">Hyperbolic tangent (Tanh(x))</span><span class="sxs-lookup"><span data-stu-id="13b00-127">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="13b00-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="13b00-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="13b00-129">Hyperbolic secant (Sech(x))</span><span class="sxs-lookup"><span data-stu-id="13b00-129">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="13b00-130">2 / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="13b00-130">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="13b00-131">Hyperbolic cosecant (Csch(x))</span><span class="sxs-lookup"><span data-stu-id="13b00-131">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="13b00-132">2 / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="13b00-132">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="13b00-133">Hyperbolic cotangent (Coth(x))</span><span class="sxs-lookup"><span data-stu-id="13b00-133">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="13b00-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="13b00-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="13b00-135">Inverse hyperbolic sine (Asinh(x))</span><span class="sxs-lookup"><span data-stu-id="13b00-135">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="13b00-136">Log(x + Sqrt(x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="13b00-136">Log(x + Sqrt(x \* x + 1))</span></span>|  
|<span data-ttu-id="13b00-137">Inverse hyperbolic cosine (Acosh(x))</span><span class="sxs-lookup"><span data-stu-id="13b00-137">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="13b00-138">Log(x + Sqrt(x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="13b00-138">Log(x + Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="13b00-139">Inverse hyperbolic tangent (Atanh(x))</span><span class="sxs-lookup"><span data-stu-id="13b00-139">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="13b00-140">Log((1 + x) / (1 – x)) / 2</span><span class="sxs-lookup"><span data-stu-id="13b00-140">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="13b00-141">Inverse hyperbolic secant (AsecH(x))</span><span class="sxs-lookup"><span data-stu-id="13b00-141">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="13b00-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="13b00-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="13b00-143">Inverse hyperbolic cosecant (Acsch(x))</span><span class="sxs-lookup"><span data-stu-id="13b00-143">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="13b00-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="13b00-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="13b00-145">Inverse hyperbolic cotangent (Acoth(x))</span><span class="sxs-lookup"><span data-stu-id="13b00-145">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="13b00-146">Log((x + 1) / (x – 1)) / 2</span><span class="sxs-lookup"><span data-stu-id="13b00-146">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="13b00-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="13b00-147">See also</span></span>

- [<span data-ttu-id="13b00-148">数値演算関数</span><span class="sxs-lookup"><span data-stu-id="13b00-148">Math Functions</span></span>](../../../visual-basic/language-reference/functions/math-functions.md)
