---
title: ICorDebugNativeFrame::GetLocalRegisterValue メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalRegisterValue
helpviewer_keywords:
- GetLocalRegisterValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalRegisterValue method [.NET Framework debugging]
ms.assetid: 5ccb74f3-f891-430c-b70a-e370624edde2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f53c8290271391e52176f8364b592ce6b46faf71
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195944"
---
# <a name="icordebugnativeframegetlocalregistervalue-method"></a><span data-ttu-id="ea5ac-102">ICorDebugNativeFrame::GetLocalRegisterValue メソッド</span><span class="sxs-lookup"><span data-stu-id="ea5ac-102">ICorDebugNativeFrame::GetLocalRegisterValue Method</span></span>
<span data-ttu-id="ea5ac-103">このネイティブ フレームに指定されたレジスタに格納されているローカル変数または引数の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="ea5ac-103">Gets the value of an argument or local variable that is stored in the specified register for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea5ac-104">構文</span><span class="sxs-lookup"><span data-stu-id="ea5ac-104">Syntax</span></span>  
  
```  
HRESULT GetLocalRegisterValue (  
    [in]  CorDebugRegister   reg,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea5ac-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ea5ac-105">Parameters</span></span>  
 `reg`  
 <span data-ttu-id="ea5ac-106">[in]値を含むレジスタを指定する"CorDebugRegister"列挙型の値。</span><span class="sxs-lookup"><span data-stu-id="ea5ac-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="ea5ac-107">[in]によって参照されているバイナリ メタデータ シグネチャのサイズを指定する整数、`pvSigBlob`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="ea5ac-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="ea5ac-108">[in]A`PCCOR_SIGNATURE`値の型のバイナリ メタデータ シグネチャを示す値。</span><span class="sxs-lookup"><span data-stu-id="ea5ac-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="ea5ac-109">[out]指定されたレジスタに格納されている取得した値を表す"ICorDebugValue"オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ea5ac-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea5ac-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="ea5ac-110">Remarks</span></span>  
 <span data-ttu-id="ea5ac-111">`GetLocalRegisterValue`ネイティブ フレームまたはの just-in-time (JIT) で、メソッドを使用できます-フレームをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="ea5ac-111">The `GetLocalRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea5ac-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="ea5ac-112">Requirements</span></span>  
 <span data-ttu-id="ea5ac-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea5ac-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea5ac-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ea5ac-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ea5ac-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea5ac-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ea5ac-116">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="ea5ac-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ea5ac-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea5ac-117">See also</span></span>
