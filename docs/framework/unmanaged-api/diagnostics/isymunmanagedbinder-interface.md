---
title: ISymUnmanagedBinder インターフェイス
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder
helpviewer_keywords:
- ISymUnmanagedBinder interface [.NET Framework debugging]
ms.assetid: b22fbe19-b30f-4696-8175-e6b91da9edab
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b6d91f68ac737ce28cdbef926119bb3711bc1096
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940063"
---
# <a name="isymunmanagedbinder-interface"></a><span data-ttu-id="ad28f-102">ISymUnmanagedBinder インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad28f-102">ISymUnmanagedBinder Interface</span></span>
<span data-ttu-id="ad28f-103">アンマネージ コードのシンボル バインダーを表します。</span><span class="sxs-lookup"><span data-stu-id="ad28f-103">Represents a symbol binder for unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ad28f-104">信頼できないソースからプログラム データベース (PDB) ファイルをセキュリティ リスクになります。</span><span class="sxs-lookup"><span data-stu-id="ad28f-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ad28f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="ad28f-105">Methods</span></span>  
  
|<span data-ttu-id="ad28f-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="ad28f-106">Method</span></span>|<span data-ttu-id="ad28f-107">説明</span><span class="sxs-lookup"><span data-stu-id="ad28f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ad28f-108">GetReaderForFile メソッド</span><span class="sxs-lookup"><span data-stu-id="ad28f-108">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|<span data-ttu-id="ad28f-109">メタデータ インターフェイスおよびファイル名を指定されたを返します、正しい[ISymUnmanagedReader](isymunmanagedreader-interface.md)構造体、モジュールに関連付けられているデバッグ シンボルを読み取る。</span><span class="sxs-lookup"><span data-stu-id="ad28f-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols associated with the module.</span></span>|  
|[<span data-ttu-id="ad28f-110">GetReaderFromStream メソッド</span><span class="sxs-lookup"><span data-stu-id="ad28f-110">GetReaderFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|<span data-ttu-id="ad28f-111">メタデータ インターフェイスとシンボル ストアを格納しているストリームでは、指定されたを返します、正しい[ISymUnmanagedReader](isymunmanagedreader-interface.md)構造は、デバッグを読み取ることが特定のシンボル ストアからシンボルします。</span><span class="sxs-lookup"><span data-stu-id="ad28f-111">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ad28f-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="ad28f-112">Requirements</span></span>  
 <span data-ttu-id="ad28f-113">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ad28f-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad28f-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad28f-114">See also</span></span>

- [<span data-ttu-id="ad28f-115">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad28f-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="ad28f-116">ISymUnmanagedBinder2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad28f-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="ad28f-117">ISymUnmanagedBinder3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad28f-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
