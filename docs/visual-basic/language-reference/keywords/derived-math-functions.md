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
ms.openlocfilehash: f84b1ef18ef2a924bb2e47da85ecbb51f982873a
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869024"
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="156ba-102">数値演算関数の導出 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="156ba-102">Derived Math Functions (Visual Basic)</span></span>

<span data-ttu-id="156ba-103">次の表に、<xref:System.Math?displayProperty=nameWithType> オブジェクトの組み込み数学関数から導出できる非組み込み数学関数を示します。</span><span class="sxs-lookup"><span data-stu-id="156ba-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="156ba-104">組み込み数学関数にアクセスするには、ファイルまたはプロジェクトに `Imports System.Math` を追加します。</span><span class="sxs-lookup"><span data-stu-id="156ba-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="156ba-105">関数</span><span class="sxs-lookup"><span data-stu-id="156ba-105">Function</span></span>|<span data-ttu-id="156ba-106">導出した同等物</span><span class="sxs-lookup"><span data-stu-id="156ba-106">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="156ba-107">Secant (Sec(x))</span><span class="sxs-lookup"><span data-stu-id="156ba-107">Secant (Sec(x))</span></span>|<span data-ttu-id="156ba-108">1 / Cos(x)</span><span class="sxs-lookup"><span data-stu-id="156ba-108">1 / Cos(x)</span></span>|  
|<span data-ttu-id="156ba-109">Cosecant (Csc(x))</span><span class="sxs-lookup"><span data-stu-id="156ba-109">Cosecant (Csc(x))</span></span>|<span data-ttu-id="156ba-110">1 / Sin(x)</span><span class="sxs-lookup"><span data-stu-id="156ba-110">1 / Sin(x)</span></span>|  
|<span data-ttu-id="156ba-111">Cotangent (Ctan(x))</span><span class="sxs-lookup"><span data-stu-id="156ba-111">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="156ba-112">1 / Tan(x)</span><span class="sxs-lookup"><span data-stu-id="156ba-112">1 / Tan(x)</span></span>|  
|<span data-ttu-id="156ba-113">Inverse sine (Asin(x))</span><span class="sxs-lookup"><span data-stu-id="156ba-113">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="156ba-114">Atan(x / Sqrt(-x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="156ba-114">Atan(x / Sqrt(-x \* x + 1))</span></span>|  
|<span data-ttu-id="156ba-115">Inverse cosine (Acos(x))</span><span class="sxs-lookup"><span data-stu-id="156ba-115">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="156ba-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span><span class="sxs-lookup"><span data-stu-id="156ba-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="156ba-117">Inverse secant (Asec(x))</span><span class="sxs-lookup"><span data-stu-id="156ba-117">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="156ba-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="156ba-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="156ba-119">Inverse cosecant (Acsc(x))</span><span class="sxs-lookup"><span data-stu-id="156ba-119">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="156ba-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="156ba-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="156ba-121">Inverse cotangent (Acot(x))</span><span class="sxs-lookup"><span data-stu-id="156ba-121">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="156ba-122">2 \* Atan(1) - Atan(x)</span><span class="sxs-lookup"><span data-stu-id="156ba-122">2 \* Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="156ba-123">Hyperbolic sine (Sinh(x))</span><span class="sxs-lookup"><span data-stu-id="156ba-123">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="156ba-124">(Exp(x) – Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="156ba-124">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="156ba-125">Hyperbolic cosine (Cosh(x))</span><span class="sxs-lookup"><span data-stu-id="156ba-125">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="156ba-126">(Exp(x) + Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="156ba-126">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="156ba-127">Hyperbolic tangent (Tanh(x))</span><span class="sxs-lookup"><span data-stu-id="156ba-127">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="156ba-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="156ba-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="156ba-129">Hyperbolic secant (Sech(x))</span><span class="sxs-lookup"><span data-stu-id="156ba-129">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="156ba-130">2 / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="156ba-130">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="156ba-131">Hyperbolic cosecant (Csch(x))</span><span class="sxs-lookup"><span data-stu-id="156ba-131">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="156ba-132">2 / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="156ba-132">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="156ba-133">Hyperbolic cotangent (Coth(x))</span><span class="sxs-lookup"><span data-stu-id="156ba-133">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="156ba-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="156ba-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="156ba-135">Inverse hyperbolic sine (Asinh(x))</span><span class="sxs-lookup"><span data-stu-id="156ba-135">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="156ba-136">Log(x + Sqrt(x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="156ba-136">Log(x + Sqrt(x \* x + 1))</span></span>|  
|<span data-ttu-id="156ba-137">Inverse hyperbolic cosine (Acosh(x))</span><span class="sxs-lookup"><span data-stu-id="156ba-137">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="156ba-138">Log(x + Sqrt(x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="156ba-138">Log(x + Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="156ba-139">Inverse hyperbolic tangent (Atanh(x))</span><span class="sxs-lookup"><span data-stu-id="156ba-139">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="156ba-140">Log((1 + x) / (1 – x)) / 2</span><span class="sxs-lookup"><span data-stu-id="156ba-140">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="156ba-141">Inverse hyperbolic secant (AsecH(x))</span><span class="sxs-lookup"><span data-stu-id="156ba-141">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="156ba-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="156ba-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="156ba-143">Inverse hyperbolic cosecant (Acsch(x))</span><span class="sxs-lookup"><span data-stu-id="156ba-143">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="156ba-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="156ba-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="156ba-145">Inverse hyperbolic cotangent (Acoth(x))</span><span class="sxs-lookup"><span data-stu-id="156ba-145">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="156ba-146">Log((x + 1) / (x – 1)) / 2</span><span class="sxs-lookup"><span data-stu-id="156ba-146">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="156ba-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="156ba-147">See also</span></span>

- [<span data-ttu-id="156ba-148">数値演算関数</span><span class="sxs-lookup"><span data-stu-id="156ba-148">Math Functions</span></span>](../functions/math-functions.md)
