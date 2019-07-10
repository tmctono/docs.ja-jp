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
ms.openlocfilehash: 23228c1414f5f6327cfb326c95a3224ae231a033
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776784"
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="18a4b-102">ISymUnmanagedDispose::Destroy メソッド</span><span class="sxs-lookup"><span data-stu-id="18a4b-102">ISymUnmanagedDispose::Destroy Method</span></span>
<span data-ttu-id="18a4b-103">基になるオブジェクトを内部参照をすべて解放し、後続のメソッド呼び出しでエラーを返します。</span><span class="sxs-lookup"><span data-stu-id="18a4b-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18a4b-104">構文</span><span class="sxs-lookup"><span data-stu-id="18a4b-104">Syntax</span></span>  
  
```cpp  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="18a4b-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="18a4b-105">Return Value</span></span>  
 <span data-ttu-id="18a4b-106">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="18a4b-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18a4b-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="18a4b-107">Requirements</span></span>  
 <span data-ttu-id="18a4b-108">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="18a4b-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18a4b-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="18a4b-109">See also</span></span>

- [<span data-ttu-id="18a4b-110">ISymUnmanagedDispose インターフェイス</span><span class="sxs-lookup"><span data-stu-id="18a4b-110">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)
