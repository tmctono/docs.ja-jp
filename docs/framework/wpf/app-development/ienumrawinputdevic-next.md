---
title: IEnumRAWINPUTDEVIC:Next
ms.date: 03/30/2017
helpviewer_keywords:
- Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
ms.openlocfilehash: 05867af48b64cd1898b13fa055859c8cc0367c8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949579"
---
# <a name="ienumrawinputdevicnext"></a><span data-ttu-id="c9376-102">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="c9376-102">IEnumRAWINPUTDEVIC:Next</span></span>
<span data-ttu-id="c9376-103">次の列挙`celt` [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice)構造体、列挙子の一覧で、それらを返す`rgelt`で列挙された要素の実際の数とともに`pceltFetched`します。</span><span class="sxs-lookup"><span data-stu-id="c9376-103">Enumerates the next `celt` [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) structures in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9376-104">構文</span><span class="sxs-lookup"><span data-stu-id="c9376-104">Syntax</span></span>  
  
```  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9376-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c9376-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="c9376-106">[in]数[RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice)構造体で返される`rgelt`します。</span><span class="sxs-lookup"><span data-stu-id="c9376-106">[in] Number of [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) structures returned in `rgelt`.</span></span>  
  
 `rgelt`  
  
 <span data-ttu-id="c9376-107">[out] 列挙された RAWINPUTDEVICE 構造体を受け取る size celt (またはそれ以上) の配列。</span><span class="sxs-lookup"><span data-stu-id="c9376-107">[out] Array of size celt (or larger) to receive enumerated RAWINPUTDEVICE structures.</span></span>  
  
 `pceltFetched`  
  
 <span data-ttu-id="c9376-108">[out] `rgelt` に実際に指定された要素の数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c9376-108">[out] Pointer to the number of elements actually supplied in `rgelt`.</span></span> <span data-ttu-id="c9376-109">`NULL` が 1 の場合、呼び出し元は `rgelt` に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="c9376-109">Caller can pass in `NULL` if `rgelt` is one.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="c9376-110">プロパティ値/戻り値</span><span class="sxs-lookup"><span data-stu-id="c9376-110">Property Value/Return Value</span></span>  
 <span data-ttu-id="c9376-111">HRESULT:指定された要素の数は場合は S_OK `celt`;それ以外の場合は S_FALSE。</span><span class="sxs-lookup"><span data-stu-id="c9376-111">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
