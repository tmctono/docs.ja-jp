---
title: ISymUnmanagedDispose::Destroy メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDispose.Destroy
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDispose::Destroy
helpviewer_keywords:
- ISymUnmanagedDispose::Destroy method [.NET Framework debugging]
- Destroy method [.NET Framework debugging]
ms.assetid: a854ab9f-d2ba-470e-867f-808c1e7bd07a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 51d2f0aedffdd88974a8184954ecbb9a231b70c6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939946"
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="e6b2b-102">ISymUnmanagedDispose::Destroy メソッド</span><span class="sxs-lookup"><span data-stu-id="e6b2b-102">ISymUnmanagedDispose::Destroy Method</span></span>
<span data-ttu-id="e6b2b-103">基になるオブジェクトを内部参照をすべて解放し、後続のメソッド呼び出しでエラーを返します。</span><span class="sxs-lookup"><span data-stu-id="e6b2b-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6b2b-104">構文</span><span class="sxs-lookup"><span data-stu-id="e6b2b-104">Syntax</span></span>  
  
```  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e6b2b-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="e6b2b-105">Return Value</span></span>  
 <span data-ttu-id="e6b2b-106">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="e6b2b-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6b2b-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="e6b2b-107">Requirements</span></span>  
 <span data-ttu-id="e6b2b-108">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e6b2b-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6b2b-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6b2b-109">See also</span></span>

- [<span data-ttu-id="e6b2b-110">ISymUnmanagedDispose インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e6b2b-110">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)
