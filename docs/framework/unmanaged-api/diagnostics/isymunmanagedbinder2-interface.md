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
ms.openlocfilehash: 8300e3a7b324a2ff4acabeb30b30d2cdabc7c776
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449322"
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="14c9e-102">ISymUnmanagedBinder2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="14c9e-102">ISymUnmanagedBinder2 Interface</span></span>
<span data-ttu-id="14c9e-103">アンマネージコードのシンボルバインダーを表し、 [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="14c9e-103">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="14c9e-104">信頼されていないソースからプログラムデータベース (PDB) ファイルを開くと、セキュリティ上の危険があります。</span><span class="sxs-lookup"><span data-stu-id="14c9e-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="14c9e-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="14c9e-105">Methods</span></span>  
  
|<span data-ttu-id="14c9e-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="14c9e-106">Method</span></span>|<span data-ttu-id="14c9e-107">説明</span><span class="sxs-lookup"><span data-stu-id="14c9e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="14c9e-108">GetReaderForFile2 メソッド</span><span class="sxs-lookup"><span data-stu-id="14c9e-108">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="14c9e-109">メタデータインターフェイスとファイル名を指定すると、モジュールに関連付けられているデバッグシンボルを読み取る正しい[ISymUnmanagedReader](isymunmanagedreader-interface.md)インターフェイスが返されます。</span><span class="sxs-lookup"><span data-stu-id="14c9e-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="14c9e-110">[ISymUnmanagedBinder:: GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)メソッドよりも広範な検索を提供します。</span><span class="sxs-lookup"><span data-stu-id="14c9e-110">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="14c9e-111">要件</span><span class="sxs-lookup"><span data-stu-id="14c9e-111">Requirements</span></span>  
 <span data-ttu-id="14c9e-112">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="14c9e-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14c9e-113">参照</span><span class="sxs-lookup"><span data-stu-id="14c9e-113">See also</span></span>

- [<span data-ttu-id="14c9e-114">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="14c9e-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="14c9e-115">ISymUnmanagedBinder インターフェイス</span><span class="sxs-lookup"><span data-stu-id="14c9e-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="14c9e-116">ISymUnmanagedBinder3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="14c9e-116">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
