---
title: ISymUnmanagedMethod::GetScopeFromOffset メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetScopeFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetScopeFromOffset
helpviewer_keywords:
- GetScopeFromOffset method [.NET Framework debugging]
- ISymUnmanagedMethod::GetScopeFromOffset method [.NET Framework debugging]
ms.assetid: d14cf210-81f8-46e1-8b19-6ddec0ba8b11
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b036c5cff5300377580fe22dc254911fbdd79715
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57503126"
---
# <a name="isymunmanagedmethodgetscopefromoffset-method"></a><span data-ttu-id="44fe5-102">ISymUnmanagedMethod::GetScopeFromOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="44fe5-102">ISymUnmanagedMethod::GetScopeFromOffset Method</span></span>
<span data-ttu-id="44fe5-103">このメソッドを指定したオフセットを囲む内で最も外側の構文のスコープを取得します。</span><span class="sxs-lookup"><span data-stu-id="44fe5-103">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span> <span data-ttu-id="44fe5-104">ローカル変数の検索を開始するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="44fe5-104">This can be used to start local variable searches.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44fe5-105">構文</span><span class="sxs-lookup"><span data-stu-id="44fe5-105">Syntax</span></span>  
  
```  
HRESULT GetScopeFromOffset(  
    [in]  ULONG32 offset,  
    [out, retval] ISymUnmanagedScope**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44fe5-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="44fe5-106">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="44fe5-107">[in]A`ULONG`オフセットを格納しています。</span><span class="sxs-lookup"><span data-stu-id="44fe5-107">[in] A `ULONG` that contains the offset.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="44fe5-108">[out]設定されているポインターに返された[ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="44fe5-108">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="44fe5-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="44fe5-109">Return Value</span></span>  
 <span data-ttu-id="44fe5-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="44fe5-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44fe5-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="44fe5-111">Requirements</span></span>  
 <span data-ttu-id="44fe5-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="44fe5-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44fe5-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="44fe5-113">See also</span></span>
- [<span data-ttu-id="44fe5-114">ISymUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="44fe5-114">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
