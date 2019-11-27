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
ms.openlocfilehash: 47477bb473df8b568844d07bea704df681c9b95d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448608"
---
# <a name="isymencunmanagedmethod-interface"></a><span data-ttu-id="ad1d5-102">ISymENCUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad1d5-102">ISymENCUnmanagedMethod Interface</span></span>
<span data-ttu-id="ad1d5-103">エディットコンティニュ機能に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="ad1d5-103">Provides information for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ad1d5-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="ad1d5-104">Methods</span></span>  
  
|<span data-ttu-id="ad1d5-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="ad1d5-105">Method</span></span>|<span data-ttu-id="ad1d5-106">説明</span><span class="sxs-lookup"><span data-stu-id="ad1d5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ad1d5-107">GetDocumentsForMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="ad1d5-107">GetDocumentsForMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethod-method.md)|<span data-ttu-id="ad1d5-108">このメソッドに行が含まれているドキュメントを取得します。</span><span class="sxs-lookup"><span data-stu-id="ad1d5-108">Gets the documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="ad1d5-109">GetDocumentsForMethodCount メソッド</span><span class="sxs-lookup"><span data-stu-id="ad1d5-109">GetDocumentsForMethodCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethodcount-method.md)|<span data-ttu-id="ad1d5-110">このメソッドに行があるドキュメントの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="ad1d5-110">Gets the number of documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="ad1d5-111">GetFileNameFromOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="ad1d5-111">GetFileNameFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getfilenamefromoffset-method.md)|<span data-ttu-id="ad1d5-112">オフセットに関連付けられた行のファイル名を取得します。</span><span class="sxs-lookup"><span data-stu-id="ad1d5-112">Gets the file name for the line associated with an offset.</span></span>|  
|[<span data-ttu-id="ad1d5-113">GetLineFromOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="ad1d5-113">GetLineFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getlinefromoffset-method.md)|<span data-ttu-id="ad1d5-114">オフセットに関連付けられている行情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="ad1d5-114">Gets the line information associated with an offset.</span></span>|  
|[<span data-ttu-id="ad1d5-115">GetSourceExtentInDocument メソッド</span><span class="sxs-lookup"><span data-stu-id="ad1d5-115">GetSourceExtentInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getsourceextentindocument-method.md)|<span data-ttu-id="ad1d5-116">特定のドキュメント内のメソッドの最小の開始行と最大の終了行を取得します。</span><span class="sxs-lookup"><span data-stu-id="ad1d5-116">Gets the smallest start line and largest end line for the method in a specific document.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ad1d5-117">要件</span><span class="sxs-lookup"><span data-stu-id="ad1d5-117">Requirements</span></span>  
 <span data-ttu-id="ad1d5-118">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="ad1d5-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad1d5-119">参照</span><span class="sxs-lookup"><span data-stu-id="ad1d5-119">See also</span></span>

- [<span data-ttu-id="ad1d5-120">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad1d5-120">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
