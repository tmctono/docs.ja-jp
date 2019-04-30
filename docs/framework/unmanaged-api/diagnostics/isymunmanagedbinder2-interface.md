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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 38de9fa878db18222d2666ba86420ca856e4b121
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940037"
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="7fe2d-102">ISymUnmanagedBinder2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7fe2d-102">ISymUnmanagedBinder2 Interface</span></span>
<span data-ttu-id="7fe2d-103">アンマネージ コードのシンボル バインダーを表し、拡張、 [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="7fe2d-103">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7fe2d-104">信頼できないソースからプログラム データベース (PDB) ファイルをセキュリティ リスクになります。</span><span class="sxs-lookup"><span data-stu-id="7fe2d-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7fe2d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="7fe2d-105">Methods</span></span>  
  
|<span data-ttu-id="7fe2d-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="7fe2d-106">Method</span></span>|<span data-ttu-id="7fe2d-107">説明</span><span class="sxs-lookup"><span data-stu-id="7fe2d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7fe2d-108">GetReaderForFile2 メソッド</span><span class="sxs-lookup"><span data-stu-id="7fe2d-108">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="7fe2d-109">メタデータ インターフェイスおよびファイル名を指定されたを返します、正しい[ISymUnmanagedReader](isymunmanagedreader-interface.md)をモジュールに関連付けられているデバッグ シンボルを読み取る。</span><span class="sxs-lookup"><span data-stu-id="7fe2d-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="7fe2d-110">広範な検索の提供、 [isymunmanagedbinder::getreaderforfile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="7fe2d-110">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7fe2d-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="7fe2d-111">Requirements</span></span>  
 <span data-ttu-id="7fe2d-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7fe2d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fe2d-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="7fe2d-113">See also</span></span>

- [<span data-ttu-id="7fe2d-114">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7fe2d-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="7fe2d-115">ISymUnmanagedBinder インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7fe2d-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="7fe2d-116">ISymUnmanagedBinder3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7fe2d-116">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
