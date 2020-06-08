---
title: ISymUnmanagedBinder2 インターフェイス
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder2 Interface
helpviewer_keywords:
- ISymUnmanagedBinder2 interface [.NET Framework debugging]
ms.assetid: 7a59f405-73e8-4434-8bcc-a9dc45ea08e6
topic_type:
- apiref
ms.openlocfilehash: f6155eb777b5071ff522af4f27d5fb2d73aa25ef
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501834"
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="70a0f-102">ISymUnmanagedBinder2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="70a0f-102">ISymUnmanagedBinder2 Interface</span></span>
<span data-ttu-id="70a0f-103">アンマネージコードのシンボルバインダーを表し、 [ISymUnmanagedBinder](isymunmanagedbinder-interface.md)インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="70a0f-103">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="70a0f-104">信頼されていないソースからプログラムデータベース (PDB) ファイルを開くと、セキュリティ上の危険があります。</span><span class="sxs-lookup"><span data-stu-id="70a0f-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="70a0f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="70a0f-105">Methods</span></span>  
  
|<span data-ttu-id="70a0f-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="70a0f-106">Method</span></span>|<span data-ttu-id="70a0f-107">説明</span><span class="sxs-lookup"><span data-stu-id="70a0f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="70a0f-108">GetReaderForFile2 メソッド</span><span class="sxs-lookup"><span data-stu-id="70a0f-108">GetReaderForFile2 Method</span></span>](isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="70a0f-109">メタデータインターフェイスとファイル名を指定すると、モジュールに関連付けられているデバッグシンボルを読み取る正しい[ISymUnmanagedReader](isymunmanagedreader-interface.md)インターフェイスが返されます。</span><span class="sxs-lookup"><span data-stu-id="70a0f-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="70a0f-110">[ISymUnmanagedBinder:: GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md)メソッドよりも広範な検索を提供します。</span><span class="sxs-lookup"><span data-stu-id="70a0f-110">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="70a0f-111">要件</span><span class="sxs-lookup"><span data-stu-id="70a0f-111">Requirements</span></span>  
 <span data-ttu-id="70a0f-112">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="70a0f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70a0f-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="70a0f-113">See also</span></span>

- [<span data-ttu-id="70a0f-114">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="70a0f-114">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="70a0f-115">ISymUnmanagedBinder インターフェイス</span><span class="sxs-lookup"><span data-stu-id="70a0f-115">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
- [<span data-ttu-id="70a0f-116">ISymUnmanagedBinder3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="70a0f-116">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)
