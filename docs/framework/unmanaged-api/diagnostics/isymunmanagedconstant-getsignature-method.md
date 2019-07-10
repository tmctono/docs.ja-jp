---
title: ISymUnmanagedConstant::GetSignature メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetSignature method [.NET Framework debugging]
ms.assetid: 3eb41151-a228-43e3-ba8f-e6dd3ceb8542
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5d479e9f55cf7d7a13fef99f302bfd8d9d89d47f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776945"
---
# <a name="isymunmanagedconstantgetsignature-method"></a><span data-ttu-id="5780f-102">ISymUnmanagedConstant::GetSignature メソッド</span><span class="sxs-lookup"><span data-stu-id="5780f-102">ISymUnmanagedConstant::GetSignature Method</span></span>
<span data-ttu-id="5780f-103">定数の署名を取得します。</span><span class="sxs-lookup"><span data-stu-id="5780f-103">Gets the signature of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5780f-104">構文</span><span class="sxs-lookup"><span data-stu-id="5780f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5780f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5780f-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="5780f-106">[in]バッファーの長さを`pcSig`パラメーターを指します。</span><span class="sxs-lookup"><span data-stu-id="5780f-106">[in] The length of the buffer that the `pcSig` parameter points to.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="5780f-107">[out]ポインター、`ULONG32`シグネチャの格納に必要なバッファーの文字のサイズを受け取る。</span><span class="sxs-lookup"><span data-stu-id="5780f-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="5780f-108">[out]シグネチャを格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="5780f-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5780f-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="5780f-109">Return Value</span></span>  
 <span data-ttu-id="5780f-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="5780f-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5780f-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="5780f-111">Requirements</span></span>  
 <span data-ttu-id="5780f-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5780f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5780f-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="5780f-113">See also</span></span>

- [<span data-ttu-id="5780f-114">ISymUnmanagedConstant インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5780f-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="5780f-115">GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="5780f-115">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="5780f-116">GetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="5780f-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
