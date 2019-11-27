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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349848"
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="3c060-102">数値演算関数の導出 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c060-102">Derived Math Functions (Visual Basic)</span></span>
<span data-ttu-id="3c060-103">次の表は、<xref:System.Math?displayProperty=nameWithType> オブジェクトの組み込みの数学関数から派生できる非組み込みの数学関数を示しています。</span><span class="sxs-lookup"><span data-stu-id="3c060-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="3c060-104">組み込みの数学関数にアクセスするには、ファイルまたはプロジェクトに `Imports System.Math` を追加します。</span><span class="sxs-lookup"><span data-stu-id="3c060-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="3c060-105">関数</span><span class="sxs-lookup"><span data-stu-id="3c060-105">Function</span></span>|<span data-ttu-id="3c060-106">派生した同等のもの</span><span class="sxs-lookup"><span data-stu-id="3c060-106">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="3c060-107">正割 (秒 (x))</span><span class="sxs-lookup"><span data-stu-id="3c060-107">Secant (Sec(x))</span></span>|<span data-ttu-id="3c060-108">1 / Cos(x)</span><span class="sxs-lookup"><span data-stu-id="3c060-108">1 / Cos(x)</span></span>|  
|<span data-ttu-id="3c060-109">余割 (Csc (x))</span><span class="sxs-lookup"><span data-stu-id="3c060-109">Cosecant (Csc(x))</span></span>|<span data-ttu-id="3c060-110">1/Sin (x)</span><span class="sxs-lookup"><span data-stu-id="3c060-110">1 / Sin(x)</span></span>|  
|<span data-ttu-id="3c060-111">コタンジェント (Ctan (x))</span><span class="sxs-lookup"><span data-stu-id="3c060-111">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="3c060-112">1/Tan (x)</span><span class="sxs-lookup"><span data-stu-id="3c060-112">1 / Tan(x)</span></span>|  
|<span data-ttu-id="3c060-113">逆サイン (アークサイン (x))</span><span class="sxs-lookup"><span data-stu-id="3c060-113">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="3c060-114">Atan (x/Sqrt (-x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="3c060-114">Atan(x / Sqrt(-x \* x + 1))</span></span>|  
|<span data-ttu-id="3c060-115">逆余弦 (Acos (x))</span><span class="sxs-lookup"><span data-stu-id="3c060-115">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="3c060-116">Atan (-x/Sqrt (-x \* x + 1)) + 2 \* Atan (1)</span><span class="sxs-lookup"><span data-stu-id="3c060-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="3c060-117">逆正割 (Asec (x))</span><span class="sxs-lookup"><span data-stu-id="3c060-117">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="3c060-118">2 \* Atan (1) – Atan (Sign (x)/Sqrt (x \* x-1))</span><span class="sxs-lookup"><span data-stu-id="3c060-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="3c060-119">逆余割 (Acsc (x))</span><span class="sxs-lookup"><span data-stu-id="3c060-119">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="3c060-120">Atan (Sign (x)/Sqrt (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="3c060-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="3c060-121">逆コタンジェント (Acot (x))</span><span class="sxs-lookup"><span data-stu-id="3c060-121">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="3c060-122">2 \* Atan (1)-Atan (x)</span><span class="sxs-lookup"><span data-stu-id="3c060-122">2 \* Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="3c060-123">ハイパーボリックサイン (Sinh (x))</span><span class="sxs-lookup"><span data-stu-id="3c060-123">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="3c060-124">(Exp (x) – Exp (-x))/2</span><span class="sxs-lookup"><span data-stu-id="3c060-124">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="3c060-125">ハイパーボリックコサイン (Cosh (x))</span><span class="sxs-lookup"><span data-stu-id="3c060-125">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="3c060-126">(Exp (x) + Exp (-x))/2</span><span class="sxs-lookup"><span data-stu-id="3c060-126">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="3c060-127">ハイパーボリックタンジェント (Tanh (x))</span><span class="sxs-lookup"><span data-stu-id="3c060-127">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="3c060-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="3c060-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="3c060-129">ハイパーボリックの正割 (x)</span><span class="sxs-lookup"><span data-stu-id="3c060-129">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="3c060-130">2 / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="3c060-130">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="3c060-131">ハイパーボリック余割 (Csch (x))</span><span class="sxs-lookup"><span data-stu-id="3c060-131">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="3c060-132">2 / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="3c060-132">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="3c060-133">ハイパーボリックコタンジェント (Coth (x))</span><span class="sxs-lookup"><span data-stu-id="3c060-133">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="3c060-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="3c060-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="3c060-135">逆双曲線正弦 (Asinh (x))</span><span class="sxs-lookup"><span data-stu-id="3c060-135">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="3c060-136">ログ (x + Sqrt (x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="3c060-136">Log(x + Sqrt(x \* x + 1))</span></span>|  
|<span data-ttu-id="3c060-137">逆双曲線余弦 (Acosh (x))</span><span class="sxs-lookup"><span data-stu-id="3c060-137">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="3c060-138">ログ (x + Sqrt (x \* x-1))</span><span class="sxs-lookup"><span data-stu-id="3c060-138">Log(x + Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="3c060-139">逆双曲線正接 (Atanh (x))</span><span class="sxs-lookup"><span data-stu-id="3c060-139">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="3c060-140">ログ ((1 + x)/(1-x))/2</span><span class="sxs-lookup"><span data-stu-id="3c060-140">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="3c060-141">逆双曲線正割 (AsecH (x))</span><span class="sxs-lookup"><span data-stu-id="3c060-141">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="3c060-142">Log ((Sqrt (-x \* x + 1) + 1)/x)</span><span class="sxs-lookup"><span data-stu-id="3c060-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="3c060-143">逆双曲線余割 (Acsch (x))</span><span class="sxs-lookup"><span data-stu-id="3c060-143">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="3c060-144">Log ((Sign (x) \* Sqrt (x \* x + 1) + 1)/x</span><span class="sxs-lookup"><span data-stu-id="3c060-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="3c060-145">逆双曲線コタンジェント (Acoth (x))</span><span class="sxs-lookup"><span data-stu-id="3c060-145">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="3c060-146">Log ((x + 1)/(x – 1))/2</span><span class="sxs-lookup"><span data-stu-id="3c060-146">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3c060-147">参照</span><span class="sxs-lookup"><span data-stu-id="3c060-147">See also</span></span>

- [<span data-ttu-id="3c060-148">数値演算関数</span><span class="sxs-lookup"><span data-stu-id="3c060-148">Math Functions</span></span>](../../../visual-basic/language-reference/functions/math-functions.md)
