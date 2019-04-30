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
ms.openlocfilehash: fdfd8e8fc419809a3a490639ada1c533f286fe8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939998"
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="3ce4e-102">ISymUnmanagedBinder3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3ce4e-102">ISymUnmanagedBinder3 Interface</span></span>
<span data-ttu-id="3ce4e-103">シンボル バインダー インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="3ce4e-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="3ce4e-104">このインターフェイスを呼び出すことによって取得`QueryInterface`を実装するオブジェクトで、`ISymUnmanagedBinder`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="3ce4e-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3ce4e-105">信頼できないソースからプログラム データベース (PDB) ファイルをセキュリティ リスクになります。</span><span class="sxs-lookup"><span data-stu-id="3ce4e-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3ce4e-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="3ce4e-106">Methods</span></span>  
  
|<span data-ttu-id="3ce4e-107">メソッド</span><span class="sxs-lookup"><span data-stu-id="3ce4e-107">Method</span></span>|<span data-ttu-id="3ce4e-108">説明</span><span class="sxs-lookup"><span data-stu-id="3ce4e-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3ce4e-109">GetReaderFromCallback メソッド</span><span class="sxs-lookup"><span data-stu-id="3ce4e-109">GetReaderFromCallback Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="3ce4e-110">ユーザーに実装するか、コールバックを使用して指定できるように、`IID_IDiaReadExeAtRVACallback`または`IID_IDiaReadExeAtOffsetCallback`メモリからデバッグ ディレクトリ情報を取得するには</span><span class="sxs-lookup"><span data-stu-id="3ce4e-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3ce4e-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="3ce4e-111">Requirements</span></span>  
 <span data-ttu-id="3ce4e-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3ce4e-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ce4e-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ce4e-113">See also</span></span>

- [<span data-ttu-id="3ce4e-114">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3ce4e-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="3ce4e-115">ISymUnmanagedBinder インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3ce4e-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="3ce4e-116">ISymUnmanagedBinder2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3ce4e-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
