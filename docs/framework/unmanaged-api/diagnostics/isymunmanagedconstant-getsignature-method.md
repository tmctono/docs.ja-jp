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
ms.openlocfilehash: 401dfbea0da309db24f3052f462daa66e8bbef4a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449269"
---
# <a name="isymunmanagedconstantgetsignature-method"></a><span data-ttu-id="d00c5-102">ISymUnmanagedConstant::GetSignature メソッド</span><span class="sxs-lookup"><span data-stu-id="d00c5-102">ISymUnmanagedConstant::GetSignature Method</span></span>
<span data-ttu-id="d00c5-103">定数の署名を取得します。</span><span class="sxs-lookup"><span data-stu-id="d00c5-103">Gets the signature of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d00c5-104">構文</span><span class="sxs-lookup"><span data-stu-id="d00c5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d00c5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d00c5-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="d00c5-106">から`pcSig` パラメーターが指すバッファーの長さ。</span><span class="sxs-lookup"><span data-stu-id="d00c5-106">[in] The length of the buffer that the `pcSig` parameter points to.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="d00c5-107">入出力署名を格納するために必要なバッファーのサイズ (文字数) を受け取る `ULONG32` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="d00c5-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="d00c5-108">入出力署名を格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="d00c5-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d00c5-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="d00c5-109">Return Value</span></span>  
 <span data-ttu-id="d00c5-110">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="d00c5-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d00c5-111">要件</span><span class="sxs-lookup"><span data-stu-id="d00c5-111">Requirements</span></span>  
 <span data-ttu-id="d00c5-112">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="d00c5-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d00c5-113">参照</span><span class="sxs-lookup"><span data-stu-id="d00c5-113">See also</span></span>

- [<span data-ttu-id="d00c5-114">ISymUnmanagedConstant インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d00c5-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="d00c5-115">GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="d00c5-115">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="d00c5-116">GetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="d00c5-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
