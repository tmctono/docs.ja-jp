---
title: ISymUnmanagedMethod::GetNamespace メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetNamespace
helpviewer_keywords:
- ISymUnmanagedMethod::GetNamespace method [.NET Framework debugging]
- GetNamespace method [.NET Framework debugging]
ms.assetid: 7fbbac42-b966-406d-9ae9-67bf3aea74ce
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 544fffd1b230469227d6ddbe3afcba54b6a7d5c1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484590"
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="42ca8-102">ISymUnmanagedMethod::GetNamespace メソッド</span><span class="sxs-lookup"><span data-stu-id="42ca8-102">ISymUnmanagedMethod::GetNamespace Method</span></span>
<span data-ttu-id="42ca8-103">このメソッドを定義する名前空間を取得します。</span><span class="sxs-lookup"><span data-stu-id="42ca8-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42ca8-104">構文</span><span class="sxs-lookup"><span data-stu-id="42ca8-104">Syntax</span></span>  
  
```  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42ca8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="42ca8-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="42ca8-106">[out]設定されているポインターに返された[ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="42ca8-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42ca8-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="42ca8-107">Return Value</span></span>  
 <span data-ttu-id="42ca8-108">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="42ca8-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42ca8-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="42ca8-109">Requirements</span></span>  
 <span data-ttu-id="42ca8-110">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="42ca8-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42ca8-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="42ca8-111">See also</span></span>
- [<span data-ttu-id="42ca8-112">ISymUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="42ca8-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
