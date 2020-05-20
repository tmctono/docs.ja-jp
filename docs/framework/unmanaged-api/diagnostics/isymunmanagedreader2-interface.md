---
title: ISymUnmanagedReader2 インターフェイス
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2
helpviewer_keywords:
- ISymUnmanagedReader2 interface [.NET Framework debugging]
ms.assetid: a01a881b-82a3-4b3e-a3a9-9dc305c2e5f7
topic_type:
- apiref
ms.openlocfilehash: d4c5ff46d37b1292059b18920abd8042c18bbf31
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615398"
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="3d416-102">ISymUnmanagedReader2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3d416-102">ISymUnmanagedReader2 Interface</span></span>
<span data-ttu-id="3d416-103">シンボルストア内のドキュメント、メソッド、および変数へのアクセスを提供するシンボルリーダーを表します。</span><span class="sxs-lookup"><span data-stu-id="3d416-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="3d416-104">このインターフェイスは、 [ISymUnmanagedReader](isymunmanagedreader-interface.md)インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="3d416-104">This interface extends the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3d416-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="3d416-105">Methods</span></span>  
  
|<span data-ttu-id="3d416-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="3d416-106">Method</span></span>|<span data-ttu-id="3d416-107">説明</span><span class="sxs-lookup"><span data-stu-id="3d416-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3d416-108">GetMethodByVersionPreRemap メソッド</span><span class="sxs-lookup"><span data-stu-id="3d416-108">GetMethodByVersionPreRemap Method</span></span>](isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="3d416-109">メソッドトークンとエディットコンティニュバージョン番号を指定して、シンボルリーダーメソッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="3d416-109">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="3d416-110">GetMethodsInDocument メソッド</span><span class="sxs-lookup"><span data-stu-id="3d416-110">GetMethodsInDocument Method</span></span>](isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="3d416-111">指定されたドキュメントに行情報が含まれるすべてのメソッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="3d416-111">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="3d416-112">GetSymAttributePreRemap メソッド</span><span class="sxs-lookup"><span data-stu-id="3d416-112">GetSymAttributePreRemap Method</span></span>](isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="3d416-113">名前に基づいてカスタム属性を取得します。</span><span class="sxs-lookup"><span data-stu-id="3d416-113">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3d416-114">要件</span><span class="sxs-lookup"><span data-stu-id="3d416-114">Requirements</span></span>  
 <span data-ttu-id="3d416-115">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="3d416-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d416-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="3d416-116">See also</span></span>

- [<span data-ttu-id="3d416-117">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3d416-117">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="3d416-118">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3d416-118">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
