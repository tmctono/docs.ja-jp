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
ms.openlocfilehash: cfd466f48a55f8b8905f6c76cf876fb8a32d4a8f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59151399"
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="ede15-102">ISymUnmanagedMethod::GetNamespace メソッド</span><span class="sxs-lookup"><span data-stu-id="ede15-102">ISymUnmanagedMethod::GetNamespace Method</span></span>
<span data-ttu-id="ede15-103">このメソッドを定義する名前空間を取得します。</span><span class="sxs-lookup"><span data-stu-id="ede15-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ede15-104">構文</span><span class="sxs-lookup"><span data-stu-id="ede15-104">Syntax</span></span>  
  
```  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ede15-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ede15-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="ede15-106">[out]設定されているポインターに返された[ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="ede15-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ede15-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="ede15-107">Return Value</span></span>  
 <span data-ttu-id="ede15-108">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="ede15-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ede15-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="ede15-109">Requirements</span></span>  
 <span data-ttu-id="ede15-110">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ede15-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ede15-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="ede15-111">See also</span></span>

- [<span data-ttu-id="ede15-112">ISymUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ede15-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
