---
title: ICorDebugNativeFrame::GetLocalMemoryValue メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalMemoryValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalMemoryValue
helpviewer_keywords:
- GetLocalMemoryValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalMemoryValue method [.NET Framework debugging]
ms.assetid: b600b3a2-9908-42d8-8093-ab6f39e9a2c9
topic_type:
- apiref
ms.openlocfilehash: cee095003c136142052b8f946fa8227927c80ee2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096868"
---
# <a name="icordebugnativeframegetlocalmemoryvalue-method"></a><span data-ttu-id="953c5-102">ICorDebugNativeFrame::GetLocalMemoryValue メソッド</span><span class="sxs-lookup"><span data-stu-id="953c5-102">ICorDebugNativeFrame::GetLocalMemoryValue Method</span></span>
<span data-ttu-id="953c5-103">このネイティブフレームの指定したメモリ位置に格納されている引数またはローカル変数の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="953c5-103">Gets the value of an argument or local variable that is stored in the specified memory location for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="953c5-104">構文</span><span class="sxs-lookup"><span data-stu-id="953c5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalMemoryValue (  
    [in]  CORDB_ADDRESS      address,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="953c5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="953c5-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="953c5-106">から値を格納しているメモリ位置を指定する `CORDB_ADDRESS` 値。</span><span class="sxs-lookup"><span data-stu-id="953c5-106">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="953c5-107">から`pvSigBlob` パラメーターによって参照されるバイナリメタデータシグネチャのサイズを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="953c5-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="953c5-108">から値の型のバイナリメタデータシグネチャを指す `PCCOR_SIGNATURE` 値。</span><span class="sxs-lookup"><span data-stu-id="953c5-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="953c5-109">入出力指定されたメモリ位置に格納されている取得値を表す "ICorDebugValue" オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="953c5-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="953c5-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="953c5-110">Requirements</span></span>  
 <span data-ttu-id="953c5-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="953c5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="953c5-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="953c5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="953c5-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="953c5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="953c5-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="953c5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="953c5-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="953c5-115">See also</span></span>
