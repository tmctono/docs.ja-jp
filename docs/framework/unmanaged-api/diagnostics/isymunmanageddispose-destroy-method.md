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
ms.openlocfilehash: 5bd94cb851d4bb044d4ce03b97d6342a2c9652e4
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441319"
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="5fda4-102">ISymUnmanagedDispose::Destroy メソッド</span><span class="sxs-lookup"><span data-stu-id="5fda4-102">ISymUnmanagedDispose::Destroy Method</span></span>
<span data-ttu-id="5fda4-103">基になるオブジェクトがすべての内部参照を解放し、後続のメソッド呼び出しの失敗を返します。</span><span class="sxs-lookup"><span data-stu-id="5fda4-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fda4-104">構文</span><span class="sxs-lookup"><span data-stu-id="5fda4-104">Syntax</span></span>  
  
```cpp  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5fda4-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="5fda4-105">Return Value</span></span>  
 <span data-ttu-id="5fda4-106">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="5fda4-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fda4-107">要件</span><span class="sxs-lookup"><span data-stu-id="5fda4-107">Requirements</span></span>  
 <span data-ttu-id="5fda4-108">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="5fda4-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fda4-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="5fda4-109">See also</span></span>

- [<span data-ttu-id="5fda4-110">ISymUnmanagedDispose インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5fda4-110">ISymUnmanagedDispose Interface</span></span>](isymunmanageddispose-interface.md)
