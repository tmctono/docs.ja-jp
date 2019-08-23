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
ms.openlocfilehash: 21da325ee58df65ac449464f8292f2ba94d99338
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943294"
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a><span data-ttu-id="b9ecc-102">ICorDebugProcess2::GetReferenceValueFromGCHandle メソッド</span><span class="sxs-lookup"><span data-stu-id="b9ecc-102">ICorDebugProcess2::GetReferenceValueFromGCHandle Method</span></span>
<span data-ttu-id="b9ecc-103">ガベージコレクションハンドルを持つ指定したマネージオブジェクトへの参照ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="b9ecc-103">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9ecc-104">構文</span><span class="sxs-lookup"><span data-stu-id="b9ecc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9ecc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b9ecc-105">Parameters</span></span>  
 `handle`  
 <span data-ttu-id="b9ecc-106">からガベージコレクションハンドルを持つマネージオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b9ecc-106">[in] A pointer to a managed object that has a garbage collection handle.</span></span> <span data-ttu-id="b9ecc-107">この値はオブジェクト<xref:System.IntPtr>であり、マネージオブジェクト<xref:System.Runtime.InteropServices.GCHandle>のから取得できます。</span><span class="sxs-lookup"><span data-stu-id="b9ecc-107">This value is a <xref:System.IntPtr> object and can be retrieved from the <xref:System.Runtime.InteropServices.GCHandle> for the managed object.</span></span>  
  
 `pOutValue`  
 <span data-ttu-id="b9ecc-108">入出力指定したマネージオブジェクトへの参照を表す、値オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b9ecc-108">[out] A pointer to the address of an ICorDebugReferenceValue object that represents a reference to the specified managed object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9ecc-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="b9ecc-109">Remarks</span></span>  
 <span data-ttu-id="b9ecc-110">返された参照値とガベージコレクション参照値を混同しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="b9ecc-110">Do not confuse the returned reference value with a garbage collection reference value.</span></span>  
  
 <span data-ttu-id="b9ecc-111">返される参照は、通常の参照のように動作します。</span><span class="sxs-lookup"><span data-stu-id="b9ecc-111">The returned reference behaves like a normal reference.</span></span> <span data-ttu-id="b9ecc-112">ブレークポイント後にコードの実行が続行される場合は無効になります。</span><span class="sxs-lookup"><span data-stu-id="b9ecc-112">It is disabled when code execution continues after a breakpoint.</span></span> <span data-ttu-id="b9ecc-113">ターゲットオブジェクトの有効期間は、参照値の有効期間の影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="b9ecc-113">The lifetime of the target object is not affected by the lifetime of the reference value.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b9ecc-114">`GetReferenceValueFromGCHandle`メソッドでは、ハンドルは検証されません。</span><span class="sxs-lookup"><span data-stu-id="b9ecc-114">The `GetReferenceValueFromGCHandle` method does not validate the handle.</span></span> <span data-ttu-id="b9ecc-115">したがって、 `GetReferenceValueFromGCHandle`メソッドは、無効なハンドルが渡された場合に、デバッガーとデバッグされているコードの両方を破損する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b9ecc-115">Therefore, the `GetReferenceValueFromGCHandle` method can potentially corrupt both the debugger and the code being debugged if an invalid handle is passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9ecc-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="b9ecc-116">Requirements</span></span>  
 <span data-ttu-id="b9ecc-117">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9ecc-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9ecc-118">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="b9ecc-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9ecc-119">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="b9ecc-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9ecc-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9ecc-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
