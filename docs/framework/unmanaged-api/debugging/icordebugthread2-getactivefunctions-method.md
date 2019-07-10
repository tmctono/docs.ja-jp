---
title: ICorDebugThread2::GetActiveFunctions メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetActiveFunctions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetActiveFunctions
helpviewer_keywords:
- GetActiveFunctions method [.NET Framework debugging]
- ICorDebugThread2::GetActiveFunctions method [.NET Framework debugging]
ms.assetid: 27fae01a-ecec-423a-973e-24f8de55826c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fdf3998d7430348cb71af8e7dd75cf2203d380ce
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769035"
---
# <a name="icordebugthread2getactivefunctions-method"></a><span data-ttu-id="04890-102">ICorDebugThread2::GetActiveFunctions メソッド</span><span class="sxs-lookup"><span data-stu-id="04890-102">ICorDebugThread2::GetActiveFunctions Method</span></span>
<span data-ttu-id="04890-103">このスレッドのフレームのそれぞれに、アクティブな関数についての情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="04890-103">Gets information about the active function in each of this thread's frames.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04890-104">構文</span><span class="sxs-lookup"><span data-stu-id="04890-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFunctions (  
    [in]   ULONG32             cFunctions,  
    [out]  ULONG32             *pcFunctions,  
    [in, out, size_is(cFunctions), length_is(*pcFunctions)]  
        COR_ACTIVE_FUNCTION    pFunctions[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04890-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="04890-105">Parameters</span></span>  
 `cFunctions`  
 <span data-ttu-id="04890-106">[in] `pFunctions` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="04890-106">[in] The size of the `pFunctions` array.</span></span>  
  
 `pcFunctions`  
 <span data-ttu-id="04890-107">[out]返されるオブジェクトの数へのポインター、`pFunctions`配列。</span><span class="sxs-lookup"><span data-stu-id="04890-107">[out] A pointer to the number of objects returned in the `pFunctions` array.</span></span> <span data-ttu-id="04890-108">返されるオブジェクトの数は、スタック上のマネージ フレームの数と等しくなります。</span><span class="sxs-lookup"><span data-stu-id="04890-108">The number of objects returned will be equal to the number of managed frames on the stack.</span></span>  
  
 `pFunctions`  
 <span data-ttu-id="04890-109">[入力、出力]このスレッドのフレームでアクティブな関数についての情報を含む、COR_ACTIVE_FUNCTION オブジェクトの配列。</span><span class="sxs-lookup"><span data-stu-id="04890-109">[in, out] An array of COR_ACTIVE_FUNCTION objects, each of which contains information about the active functions in this thread's frames.</span></span>  
  
 <span data-ttu-id="04890-110">最初の要素は、リーフ フレームとスタックのルートに戻る ために使用されます。</span><span class="sxs-lookup"><span data-stu-id="04890-110">The first element will be used for the leaf frame, and so on back to the root of the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04890-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="04890-111">Remarks</span></span>  
 <span data-ttu-id="04890-112">場合`pFunctions`が null の入力で`GetActiveFunctions`スタック上にある関数の数のみを返します。</span><span class="sxs-lookup"><span data-stu-id="04890-112">If `pFunctions` is null on input, `GetActiveFunctions` returns only the number of functions that are on the stack.</span></span> <span data-ttu-id="04890-113">つまり場合、`pFunctions`が入力で null`GetActiveFunctions`値を返しますでのみ`pcFunctions`します。</span><span class="sxs-lookup"><span data-stu-id="04890-113">That is, If `pFunctions` is null on input, `GetActiveFunctions` returns a value only in `pcFunctions`.</span></span>  
  
 <span data-ttu-id="04890-114">`GetActiveFunctions`メソッドは、最適化として、スタック トレース内のフレームから同じ情報の取得をありありました ICorDebugILFrame オブジェクトに完全なスタック トレース フレームのみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="04890-114">The `GetActiveFunctions` method is intended as an optimization over getting the same information from frames in a stack trace, and includes only frames that would have had an ICorDebugILFrame object for them in the full stack trace.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04890-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="04890-115">Requirements</span></span>  
 <span data-ttu-id="04890-116">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="04890-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04890-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="04890-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="04890-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04890-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04890-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04890-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
