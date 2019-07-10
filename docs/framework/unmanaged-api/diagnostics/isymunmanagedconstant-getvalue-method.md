---
title: ISymUnmanagedConstant::GetValue メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetValue
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetValue
helpviewer_keywords:
- GetValue method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetValue method [.NET Framework debugging]
ms.assetid: 0036fc10-e768-47a8-b9cf-bf47faf8d194
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e89dabeeb4956d106e8d0ca83520d87f3b330e63
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776802"
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="17633-102">ISymUnmanagedConstant::GetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="17633-102">ISymUnmanagedConstant::GetValue Method</span></span>
<span data-ttu-id="17633-103">定数の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="17633-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17633-104">構文</span><span class="sxs-lookup"><span data-stu-id="17633-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17633-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="17633-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="17633-106">[out]値を受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="17633-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="17633-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="17633-107">Return Value</span></span>  
 <span data-ttu-id="17633-108">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="17633-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17633-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="17633-109">Requirements</span></span>  
 <span data-ttu-id="17633-110">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="17633-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17633-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="17633-111">See also</span></span>

- [<span data-ttu-id="17633-112">ISymUnmanagedConstant インターフェイス</span><span class="sxs-lookup"><span data-stu-id="17633-112">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="17633-113">GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="17633-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="17633-114">GetSignature メソッド</span><span class="sxs-lookup"><span data-stu-id="17633-114">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
