---
title: IEnumRAWINPUTDEVIC:Skip
ms.date: 03/30/2017
helpviewer_keywords:
- Skip method [WPF]
ms.assetid: c967b0f8-1c6a-459c-8c16-d4f08918ab65
ms.openlocfilehash: f7d7df77c54d4551025aa5a344c96083c263f455
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949761"
---
# <a name="ienumrawinputdevicskip"></a><span data-ttu-id="73e8e-102">IEnumRAWINPUTDEVIC:Skip</span><span class="sxs-lookup"><span data-stu-id="73e8e-102">IEnumRAWINPUTDEVIC:Skip</span></span>
<span data-ttu-id="73e8e-103">列挙子は、[次へ] をスキップするように指示します`celt`列挙体の要素に、[次へ] を呼び出せるように[IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md)それらの要素は返されません。</span><span class="sxs-lookup"><span data-stu-id="73e8e-103">Instructs the enumerator to skip the next `celt` elements in the enumeration so that the next call to [IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md) will not return those elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73e8e-104">構文</span><span class="sxs-lookup"><span data-stu-id="73e8e-104">Syntax</span></span>  
  
```  
HRESULT Skip( [in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73e8e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="73e8e-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="73e8e-106">[in]スキップする要素の数。</span><span class="sxs-lookup"><span data-stu-id="73e8e-106">[in] Number of elements to be skipped.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="73e8e-107">プロパティ値/戻り値</span><span class="sxs-lookup"><span data-stu-id="73e8e-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="73e8e-108">HRESULT:指定された要素の数は場合は S_OK `celt`;それ以外の場合は S_FALSE。</span><span class="sxs-lookup"><span data-stu-id="73e8e-108">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
