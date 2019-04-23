---
title: ISymUnmanagedDocument::FindClosestLine メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.FindClosestLine
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::FindClosestLine
helpviewer_keywords:
- FindClosestLine method [.NET Framework debugging]
- ISymUnmanagedDocument::FindClosestLine method [.NET Framework debugging]
ms.assetid: 628f2a04-e529-407d-841e-3b3da219a9cb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ab7df9b77b1820f291c1b1873b4dfb39e326bc34
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59193162"
---
# <a name="isymunmanageddocumentfindclosestline-method"></a><span data-ttu-id="c1b9c-102">ISymUnmanagedDocument::FindClosestLine メソッド</span><span class="sxs-lookup"><span data-stu-id="c1b9c-102">ISymUnmanagedDocument::FindClosestLine Method</span></span>
<span data-ttu-id="c1b9c-103">行を指定したシーケンス ポイントができない可能性がありますが、このドキュメントでは、シーケンス ポイントである最も近い行を返します。</span><span class="sxs-lookup"><span data-stu-id="c1b9c-103">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1b9c-104">構文</span><span class="sxs-lookup"><span data-stu-id="c1b9c-104">Syntax</span></span>  
  
```  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1b9c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c1b9c-105">Parameters</span></span>  
 `line`  
 <span data-ttu-id="c1b9c-106">[in]このドキュメント内の行。</span><span class="sxs-lookup"><span data-stu-id="c1b9c-106">[in] A line in this document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="c1b9c-107">[out]行を受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c1b9c-107">[out] A pointer to a variable that receives the line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1b9c-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="c1b9c-108">Return Value</span></span>  
 <span data-ttu-id="c1b9c-109">メソッドが成功した場合は s_ok を返します。それ以外の場合、エラー コード。</span><span class="sxs-lookup"><span data-stu-id="c1b9c-109">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1b9c-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1b9c-110">See also</span></span>

- [<span data-ttu-id="c1b9c-111">ISymUnmanagedDocument インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c1b9c-111">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
