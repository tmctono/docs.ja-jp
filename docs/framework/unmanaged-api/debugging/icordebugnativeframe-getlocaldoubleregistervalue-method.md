---
title: ICorDebugNativeFrame::GetLocalDoubleRegisterValue メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalDoubleRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue method [.NET Framework debugging]
- GetLocalDoubleRegisterValue method [.NET Framework debugging]
ms.assetid: 1f838215-ac8a-434f-8ce6-03021d3098d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed7436ff73fa9cc19790859581930875f39e499e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746286"
---
# <a name="icordebugnativeframegetlocaldoubleregistervalue-method"></a><span data-ttu-id="12fd0-102">ICorDebugNativeFrame::GetLocalDoubleRegisterValue メソッド</span><span class="sxs-lookup"><span data-stu-id="12fd0-102">ICorDebugNativeFrame::GetLocalDoubleRegisterValue Method</span></span>
<span data-ttu-id="12fd0-103">このネイティブ フレームに指定した 2 つのレジスタに格納されているローカル変数または引数の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="12fd0-103">Gets the value of an argument or local variable that is stored in the two specified registers for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12fd0-104">構文</span><span class="sxs-lookup"><span data-stu-id="12fd0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalDoubleRegisterValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CorDebugRegister   lowWordReg,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12fd0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="12fd0-105">Parameters</span></span>  
 `highWordReg`  
 <span data-ttu-id="12fd0-106">[in]値の上位ワードを含むレジスタを指定する"CorDebugRegister"列挙型の値。</span><span class="sxs-lookup"><span data-stu-id="12fd0-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordReg`  
 <span data-ttu-id="12fd0-107">[in]値、`CorDebugRegister`値の下位ワードを含むレジスタを指定する列挙体。</span><span class="sxs-lookup"><span data-stu-id="12fd0-107">[in] A value of the `CorDebugRegister` enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="12fd0-108">[in]によって参照されているバイナリ メタデータ シグネチャのサイズを指定する整数、`pvSigBlob`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="12fd0-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="12fd0-109">[in]A`PCCOR_SIGNATURE`値の型のバイナリ メタデータ シグネチャを示す値。</span><span class="sxs-lookup"><span data-stu-id="12fd0-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="12fd0-110">[out]指定されたレジスタに格納されている取得した値を表す"ICorDebugValue"オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="12fd0-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified registers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12fd0-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="12fd0-111">Remarks</span></span>  
 <span data-ttu-id="12fd0-112">`GetLocalDoubleRegisterValue`ネイティブ フレームまたはの just-in-time (JIT) で、メソッドを使用できます-フレームをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="12fd0-112">The `GetLocalDoubleRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12fd0-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="12fd0-113">Requirements</span></span>  
 <span data-ttu-id="12fd0-114">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="12fd0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12fd0-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="12fd0-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="12fd0-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12fd0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12fd0-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12fd0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12fd0-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="12fd0-118">See also</span></span>
