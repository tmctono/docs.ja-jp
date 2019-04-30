---
title: ISymUnmanagedConstant::GetName メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetName
helpviewer_keywords:
- ISymUnmanagedConstant::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedConstant interface [.NET Framework debugging]
ms.assetid: cbaca4e1-4473-459b-ba34-f1f59ce7c0ba
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1da8d89cf9ae2eed7b846774434d6ea472afbb94
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939972"
---
# <a name="isymunmanagedconstantgetname-method"></a><span data-ttu-id="80922-102">ISymUnmanagedConstant::GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="80922-102">ISymUnmanagedConstant::GetName Method</span></span>
<span data-ttu-id="80922-103">定数の名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="80922-103">Gets the name of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80922-104">構文</span><span class="sxs-lookup"><span data-stu-id="80922-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80922-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="80922-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="80922-106">[in]バッファーの長さを`szName`パラメーターを指します。</span><span class="sxs-lookup"><span data-stu-id="80922-106">[in] The length of the buffer that the `szName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="80922-107">[out]ポインター、`ULONG32`文字、終端の null を含む、名前を格納するために必要なバッファーのサイズを受け取る。</span><span class="sxs-lookup"><span data-stu-id="80922-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="80922-108">[out]名前を格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="80922-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80922-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="80922-109">Return Value</span></span>  
 <span data-ttu-id="80922-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="80922-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80922-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="80922-111">Requirements</span></span>  
 <span data-ttu-id="80922-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="80922-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80922-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="80922-113">See also</span></span>

- [<span data-ttu-id="80922-114">ISymUnmanagedConstant インターフェイス</span><span class="sxs-lookup"><span data-stu-id="80922-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="80922-115">GetSignature メソッド</span><span class="sxs-lookup"><span data-stu-id="80922-115">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
- [<span data-ttu-id="80922-116">GetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="80922-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
