---
title: 数値演算関数の導出 (Visual Basic)
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
ms.openlocfilehash: 0d0606c52d1d50fcc2fd8eea3ad2851c95b18a69
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801895"
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="24e65-102">数値演算関数の導出 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24e65-102">Derived Math Functions (Visual Basic)</span></span>
<span data-ttu-id="24e65-103">次の表はの組み込みの数学関数から派生可能な非組み込みの数学関数、<xref:System.Math?displayProperty=nameWithType>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="24e65-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="24e65-104">組み込みの数学関数を追加することでアクセスできる`Imports System.Math`ファイルまたはプロジェクトにします。</span><span class="sxs-lookup"><span data-stu-id="24e65-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="24e65-105">関数</span><span class="sxs-lookup"><span data-stu-id="24e65-105">Function</span></span>|<span data-ttu-id="24e65-106">対応する派生</span><span class="sxs-lookup"><span data-stu-id="24e65-106">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="24e65-107">Secant (Sec(x))</span><span class="sxs-lookup"><span data-stu-id="24e65-107">Secant (Sec(x))</span></span>|<span data-ttu-id="24e65-108">1 / Cos(x)</span><span class="sxs-lookup"><span data-stu-id="24e65-108">1 / Cos(x)</span></span>|  
|<span data-ttu-id="24e65-109">余割 (Csc(x))</span><span class="sxs-lookup"><span data-stu-id="24e65-109">Cosecant (Csc(x))</span></span>|<span data-ttu-id="24e65-110">1 / Sin(x)</span><span class="sxs-lookup"><span data-stu-id="24e65-110">1 / Sin(x)</span></span>|  
|<span data-ttu-id="24e65-111">コタンジェント (Ctan(x))</span><span class="sxs-lookup"><span data-stu-id="24e65-111">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="24e65-112">1 / Tan(x)</span><span class="sxs-lookup"><span data-stu-id="24e65-112">1 / Tan(x)</span></span>|  
|<span data-ttu-id="24e65-113">逆正弦 (Asin(x))</span><span class="sxs-lookup"><span data-stu-id="24e65-113">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="24e65-114">Atan(x / Sqrt(-x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="24e65-114">Atan(x / Sqrt(-x \* x + 1))</span></span>|  
|<span data-ttu-id="24e65-115">逆コサイン (Acos(x))</span><span class="sxs-lookup"><span data-stu-id="24e65-115">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="24e65-116">Atan (-x/Sqrt (-x \* x + 1)) + 2 \* Atan(1)</span><span class="sxs-lookup"><span data-stu-id="24e65-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="24e65-117">逆正割 (Asec(x))</span><span class="sxs-lookup"><span data-stu-id="24e65-117">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="24e65-118">2 \* Atan(1) – Atan(Sign(x)/Sqrt (x \* x 1))</span><span class="sxs-lookup"><span data-stu-id="24e65-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="24e65-119">逆の余割 (Acsc(x))</span><span class="sxs-lookup"><span data-stu-id="24e65-119">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="24e65-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="24e65-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="24e65-121">逆余接 (Acot(x))</span><span class="sxs-lookup"><span data-stu-id="24e65-121">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="24e65-122">2 \* Atan(1) - Atan(x)</span><span class="sxs-lookup"><span data-stu-id="24e65-122">2 \* Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="24e65-123">双曲線正弦 (Sinh(x))</span><span class="sxs-lookup"><span data-stu-id="24e65-123">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="24e65-124">(Exp(x) – Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="24e65-124">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="24e65-125">双曲線余弦 (Cosh(x))</span><span class="sxs-lookup"><span data-stu-id="24e65-125">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="24e65-126">(Exp(x) + Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="24e65-126">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="24e65-127">ハイパーボリック タンジェント (Tanh(x))</span><span class="sxs-lookup"><span data-stu-id="24e65-127">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="24e65-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="24e65-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="24e65-129">双曲線正割 (Sech(x))</span><span class="sxs-lookup"><span data-stu-id="24e65-129">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="24e65-130">2 / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="24e65-130">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="24e65-131">Hyperbolic cosecant (Csch(x))</span><span class="sxs-lookup"><span data-stu-id="24e65-131">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="24e65-132">2 / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="24e65-132">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="24e65-133">双曲線余接 (Coth(x))</span><span class="sxs-lookup"><span data-stu-id="24e65-133">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="24e65-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="24e65-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="24e65-135">逆双曲線正弦 (Asinh(x))</span><span class="sxs-lookup"><span data-stu-id="24e65-135">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="24e65-136">ログ (x + Sqrt (x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="24e65-136">Log(x + Sqrt(x \* x + 1))</span></span>|  
|<span data-ttu-id="24e65-137">逆双曲線余弦 (Acosh(x))</span><span class="sxs-lookup"><span data-stu-id="24e65-137">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="24e65-138">ログ (x + Sqrt (x \* x 1))</span><span class="sxs-lookup"><span data-stu-id="24e65-138">Log(x + Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="24e65-139">逆ハイパーボリック タンジェント (Atanh(x))</span><span class="sxs-lookup"><span data-stu-id="24e65-139">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="24e65-140">Log((1 + x) / (1 – x)) / 2</span><span class="sxs-lookup"><span data-stu-id="24e65-140">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="24e65-141">逆双曲線正割 (AsecH(x))</span><span class="sxs-lookup"><span data-stu-id="24e65-141">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="24e65-142">Log ((Sqrt (-x \* x + 1) + 1)/x)</span><span class="sxs-lookup"><span data-stu-id="24e65-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="24e65-143">逆双曲線余割 (Acsch(x))</span><span class="sxs-lookup"><span data-stu-id="24e65-143">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="24e65-144">Log((Sign(x) \* Sqrt (x \* x + 1) + 1)/x)</span><span class="sxs-lookup"><span data-stu-id="24e65-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="24e65-145">逆双曲線余接 (Acoth(x))</span><span class="sxs-lookup"><span data-stu-id="24e65-145">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="24e65-146">Log((x + 1) / (x – 1)) / 2</span><span class="sxs-lookup"><span data-stu-id="24e65-146">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="24e65-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="24e65-147">See also</span></span>

- [<span data-ttu-id="24e65-148">数値演算関数</span><span class="sxs-lookup"><span data-stu-id="24e65-148">Math Functions</span></span>](../../../visual-basic/language-reference/functions/math-functions.md)
