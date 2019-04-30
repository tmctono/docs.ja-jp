---
title: ISymENCUnmanagedMethod インターフェイス
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod
helpviewer_keywords:
- ISymENCUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: faebf594-67d5-4abf-b9c1-547fd3a1ff87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4474269688094ea6c81b06659727acfb9c2ad6c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940258"
---
# <a name="isymencunmanagedmethod-interface"></a><span data-ttu-id="18570-102">ISymENCUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="18570-102">ISymENCUnmanagedMethod Interface</span></span>
<span data-ttu-id="18570-103">エディット コンティニュの機能についてを説明します。</span><span class="sxs-lookup"><span data-stu-id="18570-103">Provides information for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="18570-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="18570-104">Methods</span></span>  
  
|<span data-ttu-id="18570-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="18570-105">Method</span></span>|<span data-ttu-id="18570-106">説明</span><span class="sxs-lookup"><span data-stu-id="18570-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="18570-107">GetDocumentsForMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="18570-107">GetDocumentsForMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethod-method.md)|<span data-ttu-id="18570-108">このメソッドの行が含まれるドキュメントを取得します。</span><span class="sxs-lookup"><span data-stu-id="18570-108">Gets the documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="18570-109">GetDocumentsForMethodCount メソッド</span><span class="sxs-lookup"><span data-stu-id="18570-109">GetDocumentsForMethodCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethodcount-method.md)|<span data-ttu-id="18570-110">このメソッドの行が含まれるドキュメントの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="18570-110">Gets the number of documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="18570-111">GetFileNameFromOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="18570-111">GetFileNameFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getfilenamefromoffset-method.md)|<span data-ttu-id="18570-112">オフセットに関連付けられている行のファイル名を取得します。</span><span class="sxs-lookup"><span data-stu-id="18570-112">Gets the file name for the line associated with an offset.</span></span>|  
|[<span data-ttu-id="18570-113">GetLineFromOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="18570-113">GetLineFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getlinefromoffset-method.md)|<span data-ttu-id="18570-114">オフセットに関連付けられている行の情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="18570-114">Gets the line information associated with an offset.</span></span>|  
|[<span data-ttu-id="18570-115">GetSourceExtentInDocument メソッド</span><span class="sxs-lookup"><span data-stu-id="18570-115">GetSourceExtentInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getsourceextentindocument-method.md)|<span data-ttu-id="18570-116">取得では、特定のドキュメントでメソッドの最大の終了行と行を最小を開始します。</span><span class="sxs-lookup"><span data-stu-id="18570-116">Gets the smallest start line and largest end line for the method in a specific document.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="18570-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="18570-117">Requirements</span></span>  
 <span data-ttu-id="18570-118">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="18570-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18570-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="18570-119">See also</span></span>

- [<span data-ttu-id="18570-120">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="18570-120">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
