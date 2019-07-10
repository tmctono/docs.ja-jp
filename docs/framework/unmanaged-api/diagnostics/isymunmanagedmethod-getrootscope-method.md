---
title: ISymUnmanagedMethod::GetRootScope メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRootScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRootScope
helpviewer_keywords:
- ISymUnmanagedMethod::GetRootScope method [.NET Framework debugging]
- GetRootScope method [.NET Framework debugging]
ms.assetid: 7d58caac-2e75-4dfa-9249-32d8a624b247
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8956d72d25f240eff653d3eefb92b68431f4e2ae
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771773"
---
# <a name="isymunmanagedmethodgetrootscope-method"></a><span data-ttu-id="df7b3-102">ISymUnmanagedMethod::GetRootScope メソッド</span><span class="sxs-lookup"><span data-stu-id="df7b3-102">ISymUnmanagedMethod::GetRootScope Method</span></span>
<span data-ttu-id="df7b3-103">このメソッド内でルート構文スコープを取得します。</span><span class="sxs-lookup"><span data-stu-id="df7b3-103">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="df7b3-104">このスコープはメソッド全体を囲みます。</span><span class="sxs-lookup"><span data-stu-id="df7b3-104">This scope encloses the entire method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df7b3-105">構文</span><span class="sxs-lookup"><span data-stu-id="df7b3-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRootScope(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df7b3-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="df7b3-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="df7b3-107">[out]設定されているポインターに返された[ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="df7b3-107">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df7b3-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="df7b3-108">Return Value</span></span>  
 <span data-ttu-id="df7b3-109">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="df7b3-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df7b3-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="df7b3-110">Requirements</span></span>  
 <span data-ttu-id="df7b3-111">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="df7b3-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df7b3-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="df7b3-112">See also</span></span>

- [<span data-ttu-id="df7b3-113">ISymUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="df7b3-113">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
