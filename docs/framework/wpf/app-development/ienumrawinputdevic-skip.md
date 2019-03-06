---
title: IEnumRAWINPUTDEVIC:Skip
ms.date: 03/30/2017
helpviewer_keywords:
- Skip method [WPF]
ms.assetid: c967b0f8-1c6a-459c-8c16-d4f08918ab65
ms.openlocfilehash: fadf7b5526598f446eb7e49640bf4d43ec7395bf
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354519"
---
# <a name="ienumrawinputdevicskip"></a><span data-ttu-id="68b44-102">IEnumRAWINPUTDEVIC:Skip</span><span class="sxs-lookup"><span data-stu-id="68b44-102">IEnumRAWINPUTDEVIC:Skip</span></span>
<span data-ttu-id="68b44-103">列挙子は、[次へ] をスキップするように指示します`celt`列挙体の要素に、[次へ] を呼び出せるように[IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md)それらの要素は返されません。</span><span class="sxs-lookup"><span data-stu-id="68b44-103">Instructs the enumerator to skip the next `celt` elements in the enumeration so that the next call to [IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md) will not return those elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68b44-104">構文</span><span class="sxs-lookup"><span data-stu-id="68b44-104">Syntax</span></span>  
  
```  
HRESULT Skip( [in] ULONG celt);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="68b44-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="68b44-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="68b44-106">[in]スキップする要素の数。</span><span class="sxs-lookup"><span data-stu-id="68b44-106">[in] Number of elements to be skipped.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="68b44-107">プロパティ値/戻り値</span><span class="sxs-lookup"><span data-stu-id="68b44-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="68b44-108">HRESULT:指定された要素の数は場合は S_OK `celt`;それ以外の場合は S_FALSE。</span><span class="sxs-lookup"><span data-stu-id="68b44-108">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
