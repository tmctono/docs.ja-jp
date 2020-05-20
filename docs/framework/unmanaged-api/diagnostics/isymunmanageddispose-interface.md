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
ms.openlocfilehash: 85b0116edadbffdea8f141c3d20142e19b053321
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "83440968"
---
# <a name="isymunmanageddispose-interface"></a><span data-ttu-id="acdc2-102">ISymUnmanagedDispose インターフェイス</span><span class="sxs-lookup"><span data-stu-id="acdc2-102">ISymUnmanagedDispose Interface</span></span>
<span data-ttu-id="acdc2-103">アンマネージリソースを破棄します。</span><span class="sxs-lookup"><span data-stu-id="acdc2-103">Disposes of unmanaged resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="acdc2-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="acdc2-104">Methods</span></span>  
  
|<span data-ttu-id="acdc2-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="acdc2-105">Method</span></span>|<span data-ttu-id="acdc2-106">説明</span><span class="sxs-lookup"><span data-stu-id="acdc2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="acdc2-107">destroy メソッド</span><span class="sxs-lookup"><span data-stu-id="acdc2-107">Destroy Method</span></span>](isymunmanageddispose-destroy-method.md)|<span data-ttu-id="acdc2-108">基になるオブジェクトがすべての内部参照を解放し、後続のメソッド呼び出しの失敗を返します。</span><span class="sxs-lookup"><span data-stu-id="acdc2-108">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="acdc2-109">要件</span><span class="sxs-lookup"><span data-stu-id="acdc2-109">Requirements</span></span>  
 <span data-ttu-id="acdc2-110">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="acdc2-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acdc2-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="acdc2-111">See also</span></span>

- [<span data-ttu-id="acdc2-112">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="acdc2-112">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
