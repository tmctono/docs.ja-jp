---
title: ISymUnmanagedDispose インターフェイス
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDispose
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDispose
helpviewer_keywords:
- ISymUnmanagedDispose interface [.NET Framework debugging]
ms.assetid: b1d74e83-a200-4d00-8fbd-27918808616d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8e81cea13fb8d25701ccbe163f112904baf47a9f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939920"
---
# <a name="isymunmanageddispose-interface"></a><span data-ttu-id="8d451-102">ISymUnmanagedDispose インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8d451-102">ISymUnmanagedDispose Interface</span></span>
<span data-ttu-id="8d451-103">アンマネージ リソースを破棄します。</span><span class="sxs-lookup"><span data-stu-id="8d451-103">Disposes of unmanaged resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8d451-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="8d451-104">Methods</span></span>  
  
|<span data-ttu-id="8d451-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="8d451-105">Method</span></span>|<span data-ttu-id="8d451-106">説明</span><span class="sxs-lookup"><span data-stu-id="8d451-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8d451-107">destroy メソッド</span><span class="sxs-lookup"><span data-stu-id="8d451-107">Destroy Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-destroy-method.md)|<span data-ttu-id="8d451-108">基になるオブジェクトを内部参照をすべて解放し、後続のメソッド呼び出しでエラーを返します。</span><span class="sxs-lookup"><span data-stu-id="8d451-108">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8d451-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="8d451-109">Requirements</span></span>  
 <span data-ttu-id="8d451-110">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8d451-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d451-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="8d451-111">See also</span></span>

- [<span data-ttu-id="8d451-112">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8d451-112">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
