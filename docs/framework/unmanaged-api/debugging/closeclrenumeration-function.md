---
title: CloseCLREnumeration 関数
ms.date: 03/30/2017
api_name:
- CloseCLREnumeration
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- CloseCLREnumeration
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CloseCLR Enumeration function
ms.assetid: 5e3c3958-80bb-43b1-a96b-dd3e6dbd9cd7
topic_type:
- apiref
ms.openlocfilehash: 1d42292705dae03e9bf1a1555508dfb69cebde82
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132434"
---
# <a name="closeclrenumeration-function"></a><span data-ttu-id="9182c-102">CloseCLREnumeration 関数</span><span class="sxs-lookup"><span data-stu-id="9182c-102">CloseCLREnumeration Function</span></span>
<span data-ttu-id="9182c-103">[列挙 Ateclrs 関数](enumerateclrs-function.md)によって返されるハンドルの配列にある有効な共通言語ランタイム (CLR) の継続スタートアップイベントをすべて閉じ、ハンドルおよび文字列パス配列のメモリを解放します。</span><span class="sxs-lookup"><span data-stu-id="9182c-103">Closes any valid common language runtime (CLR) continue-startup events located in an array of handles returned by the [EnumerateCLRs function](enumerateclrs-function.md), and frees the memory for the handle and string path arrays.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9182c-104">構文</span><span class="sxs-lookup"><span data-stu-id="9182c-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseCLREnumeration (  
    [in]  DWORD      pHandleArray,  
    [in]  LPWSTR**   pStringArray,  
    [in]  DWORD*     dwArrayLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9182c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9182c-105">Parameters</span></span>  
 `pHandleArray`  
 <span data-ttu-id="9182c-106">から[列挙機能](enumerateclrs-function.md)から返されたイベントハンドルの配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="9182c-106">[in] Pointer to the array of event handles returned from the [EnumerateCLRs function](enumerateclrs-function.md).</span></span>  
  
 `pStringArray`  
 <span data-ttu-id="9182c-107">から[列挙型 Ateclrs 関数](enumerateclrs-function.md)から返された CLR 文字列パスの配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="9182c-107">[in] Pointer to the array of CLR string paths returned from the [EnumerateCLRs function](enumerateclrs-function.md).</span></span>  
  
 `dwArrayLength`  
 <span data-ttu-id="9182c-108">[in] `pHandleArray` または `pStringArray` (これらは同じです) のサイズ (長さ) を含む DWORD。</span><span class="sxs-lookup"><span data-stu-id="9182c-108">[in] DWORD that contains the size (length) of either `pHandleArray` or `pStringArray` (they are the same).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9182c-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="9182c-109">Return Value</span></span>  
 <span data-ttu-id="9182c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9182c-110">S_OK</span></span>  
 <span data-ttu-id="9182c-111">[列挙 Ateclrs 関数](enumerateclrs-function.md)によって開かれたハンドルが閉じられ、ハンドルおよび文字列配列に割り当てられたメモリが解放されます。</span><span class="sxs-lookup"><span data-stu-id="9182c-111">Handles opened by the [EnumerateCLRs function](enumerateclrs-function.md) are closed, and memory allocated for the handle and string arrays is freed.</span></span>  
  
 <span data-ttu-id="9182c-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="9182c-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="9182c-113">`pHandleArray` の長さが、`dwArrayLength` に渡された長さと一致しません。</span><span class="sxs-lookup"><span data-stu-id="9182c-113">The length of `pHandleArray` does not match the length that is passed in `dwArrayLength`.</span></span>  
  
 <span data-ttu-id="9182c-114">E_FAIL (またはその他の E_ リターン コード)</span><span class="sxs-lookup"><span data-stu-id="9182c-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="9182c-115">`pHandleArray` および `pStringArray` のメモリを解放できません。</span><span class="sxs-lookup"><span data-stu-id="9182c-115">The function is unable to free the memory for `pHandleArray` and `pStringArray`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9182c-116">［要件］</span><span class="sxs-lookup"><span data-stu-id="9182c-116">Requirements</span></span>  
 <span data-ttu-id="9182c-117">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9182c-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9182c-118">**ヘッダー:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="9182c-118">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="9182c-119">**ライブラリ:** dbgshim .dll</span><span class="sxs-lookup"><span data-stu-id="9182c-119">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="9182c-120">**.NET Framework のバージョン:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="9182c-120">**.NET Framework Versions:** 3.5 SP1</span></span>
