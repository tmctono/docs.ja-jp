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
ms.openlocfilehash: 132e0868426670ba61d8ee12ba7007be1a8a52de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139397"
---
# <a name="icordebugnativeframegetlocalregistervalue-method"></a><span data-ttu-id="88fb7-102">ICorDebugNativeFrame::GetLocalRegisterValue メソッド</span><span class="sxs-lookup"><span data-stu-id="88fb7-102">ICorDebugNativeFrame::GetLocalRegisterValue Method</span></span>
<span data-ttu-id="88fb7-103">このネイティブフレームの指定したレジスタに格納されている引数またはローカル変数の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="88fb7-103">Gets the value of an argument or local variable that is stored in the specified register for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88fb7-104">構文</span><span class="sxs-lookup"><span data-stu-id="88fb7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalRegisterValue (  
    [in]  CorDebugRegister   reg,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88fb7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="88fb7-105">Parameters</span></span>  
 `reg`  
 <span data-ttu-id="88fb7-106">から値を含むレジスタを指定する "CorDebugRegister" 列挙の値。</span><span class="sxs-lookup"><span data-stu-id="88fb7-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="88fb7-107">から`pvSigBlob` パラメーターによって参照されるバイナリメタデータシグネチャのサイズを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="88fb7-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="88fb7-108">から値の型のバイナリメタデータシグネチャを指す `PCCOR_SIGNATURE` 値。</span><span class="sxs-lookup"><span data-stu-id="88fb7-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="88fb7-109">入出力指定したレジスタに格納されている取得した値を表す "ICorDebugValue" オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="88fb7-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="88fb7-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="88fb7-110">Remarks</span></span>  
 <span data-ttu-id="88fb7-111">`GetLocalRegisterValue` メソッドは、ネイティブフレームまたは just-in-time (JIT) でコンパイルされたフレームのどちらでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="88fb7-111">The `GetLocalRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88fb7-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="88fb7-112">Requirements</span></span>  
 <span data-ttu-id="88fb7-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88fb7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88fb7-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="88fb7-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="88fb7-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88fb7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="88fb7-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88fb7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88fb7-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="88fb7-117">See also</span></span>
