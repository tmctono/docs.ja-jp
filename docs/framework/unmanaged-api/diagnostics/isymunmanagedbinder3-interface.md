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
ms.openlocfilehash: 5a26de2a8f5439b7c81560927c991d449e57b76c
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441592"
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="164a4-102">ISymUnmanagedBinder3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="164a4-102">ISymUnmanagedBinder3 Interface</span></span>
<span data-ttu-id="164a4-103">シンボルバインダーインターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="164a4-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="164a4-104">このインターフェイスを取得するには `QueryInterface` 、インターフェイスを実装するオブジェクトに対してを呼び出し `ISymUnmanagedBinder` ます。</span><span class="sxs-lookup"><span data-stu-id="164a4-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="164a4-105">信頼されていないソースからプログラムデータベース (PDB) ファイルを開くと、セキュリティ上の危険があります。</span><span class="sxs-lookup"><span data-stu-id="164a4-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="164a4-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="164a4-106">Methods</span></span>  
  
|<span data-ttu-id="164a4-107">メソッド</span><span class="sxs-lookup"><span data-stu-id="164a4-107">Method</span></span>|<span data-ttu-id="164a4-108">説明</span><span class="sxs-lookup"><span data-stu-id="164a4-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="164a4-109">GetReaderFromCallback メソッド</span><span class="sxs-lookup"><span data-stu-id="164a4-109">GetReaderFromCallback Method</span></span>](isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="164a4-110">`IID_IDiaReadExeAtRVACallback` `IID_IDiaReadExeAtOffsetCallback` メモリからデバッグディレクトリ情報を取得するために、またはのいずれかを使用して、ユーザーがを実装または提供できるようにします。</span><span class="sxs-lookup"><span data-stu-id="164a4-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="164a4-111">要件</span><span class="sxs-lookup"><span data-stu-id="164a4-111">Requirements</span></span>  
 <span data-ttu-id="164a4-112">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="164a4-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="164a4-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="164a4-113">See also</span></span>

- [<span data-ttu-id="164a4-114">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="164a4-114">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="164a4-115">ISymUnmanagedBinder インターフェイス</span><span class="sxs-lookup"><span data-stu-id="164a4-115">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
- [<span data-ttu-id="164a4-116">ISymUnmanagedBinder2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="164a4-116">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)
