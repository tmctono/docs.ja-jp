---
title: ICorDebugProcess2::GetReferenceValueFromGCHandle メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetReferenceValueFromGCHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetReferenceValueFromGCHandle
helpviewer_keywords:
- GetReferenceValueFromGCHandle method [.NET Framework debugging]
- ICorDebugProcess2::GetReferenceValueFromGCHandle method [.NET Framework debugging]
ms.assetid: 8bdd7f4c-19f2-4ede-875e-603773e8c128
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08bf4022f7cd7f85ffe7939c16fd47950e131a77
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471525"
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a><span data-ttu-id="cf04a-102">ICorDebugProcess2::GetReferenceValueFromGCHandle メソッド</span><span class="sxs-lookup"><span data-stu-id="cf04a-102">ICorDebugProcess2::GetReferenceValueFromGCHandle Method</span></span>
<span data-ttu-id="cf04a-103">ガベージ コレクション ハンドルが、指定した管理対象のオブジェクト参照ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="cf04a-103">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf04a-104">構文</span><span class="sxs-lookup"><span data-stu-id="cf04a-104">Syntax</span></span>  
  
```  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf04a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cf04a-105">Parameters</span></span>  
 `handle`  
 <span data-ttu-id="cf04a-106">[in]ガベージ コレクション ハンドルを持つマネージ オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="cf04a-106">[in] A pointer to a managed object that has a garbage collection handle.</span></span> <span data-ttu-id="cf04a-107">この値は、<xref:System.IntPtr>オブジェクトおよびから取得できます、<xref:System.Runtime.InteropServices.GCHandle>マネージ オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="cf04a-107">This value is a <xref:System.IntPtr> object and can be retrieved from the <xref:System.Runtime.InteropServices.GCHandle> for the managed object.</span></span>  
  
 `pOutValue`  
 <span data-ttu-id="cf04a-108">[out]指定したマネージ オブジェクトへの参照を表す ICorDebugReferenceValue オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="cf04a-108">[out] A pointer to the address of an ICorDebugReferenceValue object that represents a reference to the specified managed object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf04a-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="cf04a-109">Remarks</span></span>  
 <span data-ttu-id="cf04a-110">ガベージ コレクションの参照を値で返される参照値を混同しないでください。</span><span class="sxs-lookup"><span data-stu-id="cf04a-110">Do not confuse the returned reference value with a garbage collection reference value.</span></span>  
  
 <span data-ttu-id="cf04a-111">返される参照は、通常の参照のように動作します。</span><span class="sxs-lookup"><span data-stu-id="cf04a-111">The returned reference behaves like a normal reference.</span></span> <span data-ttu-id="cf04a-112">ブレークポイントの後でコードが実行が継続する場合に無効です。</span><span class="sxs-lookup"><span data-stu-id="cf04a-112">It is disabled when code execution continues after a breakpoint.</span></span> <span data-ttu-id="cf04a-113">ターゲット オブジェクトの有効期間は参照値の有効期間の影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="cf04a-113">The lifetime of the target object is not affected by the lifetime of the reference value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf04a-114">`GetReferenceValueFromGCHandle`メソッドは、ハンドルは検証されません。</span><span class="sxs-lookup"><span data-stu-id="cf04a-114">The `GetReferenceValueFromGCHandle` method does not validate the handle.</span></span> <span data-ttu-id="cf04a-115">そのため、`GetReferenceValueFromGCHandle`デバッガーと無効なハンドルが渡された場合にデバッグ中のコードの両方、メソッドは破損可能性があることができます。</span><span class="sxs-lookup"><span data-stu-id="cf04a-115">Therefore, the `GetReferenceValueFromGCHandle` method can potentially corrupt both the debugger and the code being debugged if an invalid handle is passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf04a-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="cf04a-116">Requirements</span></span>  
 <span data-ttu-id="cf04a-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf04a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf04a-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf04a-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf04a-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf04a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf04a-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf04a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
