---
title: ISymUnmanagedBinder3 インターフェイス
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3 Interface
helpviewer_keywords:
- ISymUnmanagedBinder3 interface [.NET Framework debugging]
ms.assetid: 37527a84-4b03-4f08-8135-94d898599089
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a6f514cc070a0a38eb09a5387efc8611100765b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944105"
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="9228f-102">ISymUnmanagedBinder3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9228f-102">ISymUnmanagedBinder3 Interface</span></span>
<span data-ttu-id="9228f-103">シンボルバインダーインターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="9228f-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="9228f-104">このインターフェイスを取得する`QueryInterface`には、 `ISymUnmanagedBinder`インターフェイスを実装するオブジェクトに対してを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9228f-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9228f-105">信頼されていないソースからプログラムデータベース (PDB) ファイルを開くと、セキュリティ上の危険があります。</span><span class="sxs-lookup"><span data-stu-id="9228f-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9228f-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="9228f-106">Methods</span></span>  
  
|<span data-ttu-id="9228f-107">メソッド</span><span class="sxs-lookup"><span data-stu-id="9228f-107">Method</span></span>|<span data-ttu-id="9228f-108">説明</span><span class="sxs-lookup"><span data-stu-id="9228f-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9228f-109">GetReaderFromCallback メソッド</span><span class="sxs-lookup"><span data-stu-id="9228f-109">GetReaderFromCallback Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="9228f-110">メモリからデバッグディレクトリ情報を取得するために、 `IID_IDiaReadExeAtRVACallback`また`IID_IDiaReadExeAtOffsetCallback`はのいずれかを使用して、ユーザーがを実装または提供できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9228f-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9228f-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="9228f-111">Requirements</span></span>  
 <span data-ttu-id="9228f-112">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="9228f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9228f-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="9228f-113">See also</span></span>

- [<span data-ttu-id="9228f-114">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9228f-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="9228f-115">ISymUnmanagedBinder インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9228f-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="9228f-116">ISymUnmanagedBinder2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9228f-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
