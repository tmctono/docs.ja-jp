---
title: ICorDebugNativeFrame::GetLocalRegisterMemoryValue メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalRegisterMemoryValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalRegisterMemoryValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalRegisterMemoryValue method [.NET Framework debugging]
- GetLocalRegisterMemoryValue method [.NET Framework debugging]
ms.assetid: d350f69d-9aff-4f5a-8301-daea22dee2da
topic_type:
- apiref
ms.openlocfilehash: f16150ad7d9ecec4b4aceee5c9266e9a7859f1cb
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213297"
---
# <a name="icordebugnativeframegetlocalregistermemoryvalue-method"></a><span data-ttu-id="1175f-102">ICorDebugNativeFrame::GetLocalRegisterMemoryValue メソッド</span><span class="sxs-lookup"><span data-stu-id="1175f-102">ICorDebugNativeFrame::GetLocalRegisterMemoryValue Method</span></span>
<span data-ttu-id="1175f-103">このネイティブフレームのメモリ位置と指定したレジスタに、下位ワードと上位ワードが格納される引数またはローカル変数の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="1175f-103">Gets the value of an argument or local variable, of which the low word and high word are stored in the memory location and specified register, respectively, for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1175f-104">構文</span><span class="sxs-lookup"><span data-stu-id="1175f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalRegisterMemoryValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CORDB_ADDRESS      lowWordAddress,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1175f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1175f-105">Parameters</span></span>  
 `highWordReg`  
 <span data-ttu-id="1175f-106">から値の上位ワードを含むレジスタを指定する "CorDebugRegister" 列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="1175f-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordAddress`  
 <span data-ttu-id="1175f-107">から`CORDB_ADDRESS`値の下位ワードを格納しているメモリ位置を指定する値。</span><span class="sxs-lookup"><span data-stu-id="1175f-107">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="1175f-108">からパラメーターによって参照されるバイナリメタデータシグネチャのサイズを指定する整数 `pvSigBlob` 。</span><span class="sxs-lookup"><span data-stu-id="1175f-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="1175f-109">から`PCCOR_SIGNATURE`値の型のバイナリメタデータシグネチャを指す値。</span><span class="sxs-lookup"><span data-stu-id="1175f-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="1175f-110">入出力指定されたレジスタおよびメモリ位置に格納されている取得値を表す "ICorDebugValue" オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1175f-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register and memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1175f-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="1175f-111">Requirements</span></span>  
 <span data-ttu-id="1175f-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1175f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1175f-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1175f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1175f-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1175f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1175f-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1175f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1175f-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="1175f-116">See also</span></span>
