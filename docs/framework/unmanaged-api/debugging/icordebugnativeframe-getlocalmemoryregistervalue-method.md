---
title: ICorDebugNativeFrame::GetLocalMemoryRegisterValue メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalMemoryRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalMemoryRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalMemoryRegisterValue method [.NET Framework debugging]
- GetLocalMemoryRegisterValue method
ms.assetid: 33a19f6e-1029-4d53-af64-19591c6e58ee
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b8b871377db6da95a3d824461671241d7b163f5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746257"
---
# <a name="icordebugnativeframegetlocalmemoryregistervalue-method"></a><span data-ttu-id="f1c8a-102">ICorDebugNativeFrame::GetLocalMemoryRegisterValue メソッド</span><span class="sxs-lookup"><span data-stu-id="f1c8a-102">ICorDebugNativeFrame::GetLocalMemoryRegisterValue Method</span></span>
<span data-ttu-id="f1c8a-103">引数またはうち下位ワードと上位ワードそれぞれで格納されるメモリの場所と指定されたレジスタ、このネイティブ フレームに、ローカル変数の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="f1c8a-103">Gets the value of an argument or local variable, of which the low word and high word are stored in the specified register and memory location, respectively, for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1c8a-104">構文</span><span class="sxs-lookup"><span data-stu-id="f1c8a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalMemoryRegisterValue (  
    [in] CORDB_ADDRESS      highWordAddress,  
    [in] CorDebugRegister   lowWordRegister,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1c8a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1c8a-105">Parameters</span></span>  
 `highWordAddress`  
 <span data-ttu-id="f1c8a-106">[in]A`CORDB_ADDRESS`値の上位ワードを格納しているメモリの場所を指定する値。</span><span class="sxs-lookup"><span data-stu-id="f1c8a-106">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the high word of the value.</span></span>  
  
 `lowWordRegister`  
 <span data-ttu-id="f1c8a-107">[in]値の下位ワードを含むレジスタを指定する"CorDebugRegister"列挙型の値。</span><span class="sxs-lookup"><span data-stu-id="f1c8a-107">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="f1c8a-108">[in]によって参照されているバイナリ メタデータ シグネチャのサイズを指定する整数、`pvSigBlob`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="f1c8a-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="f1c8a-109">[in]A`PCCOR_SIGNATURE`値の型のバイナリ メタデータ シグネチャを示す値。</span><span class="sxs-lookup"><span data-stu-id="f1c8a-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="f1c8a-110">[out]指定した登録とメモリの場所に格納されている取得した値を表す"ICorDebugValue"オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f1c8a-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register and memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1c8a-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="f1c8a-111">Requirements</span></span>  
 <span data-ttu-id="f1c8a-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1c8a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1c8a-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1c8a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1c8a-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1c8a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1c8a-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1c8a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1c8a-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1c8a-116">See also</span></span>
