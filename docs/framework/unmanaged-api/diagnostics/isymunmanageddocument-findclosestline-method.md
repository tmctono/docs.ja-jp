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
ms.openlocfilehash: 8d6be64137b59c84dfadbd7f0e4895eac2fb27e4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776791"
---
# <a name="isymunmanageddocumentfindclosestline-method"></a><span data-ttu-id="3ab21-102">ISymUnmanagedDocument::FindClosestLine メソッド</span><span class="sxs-lookup"><span data-stu-id="3ab21-102">ISymUnmanagedDocument::FindClosestLine Method</span></span>
<span data-ttu-id="3ab21-103">行を指定したシーケンス ポイントができない可能性がありますが、このドキュメントでは、シーケンス ポイントである最も近い行を返します。</span><span class="sxs-lookup"><span data-stu-id="3ab21-103">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ab21-104">構文</span><span class="sxs-lookup"><span data-stu-id="3ab21-104">Syntax</span></span>  
  
```cpp  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ab21-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3ab21-105">Parameters</span></span>  
 `line`  
 <span data-ttu-id="3ab21-106">[in]このドキュメント内の行。</span><span class="sxs-lookup"><span data-stu-id="3ab21-106">[in] A line in this document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="3ab21-107">[out]行を受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="3ab21-107">[out] A pointer to a variable that receives the line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ab21-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="3ab21-108">Return Value</span></span>  
 <span data-ttu-id="3ab21-109">メソッドが成功した場合は s_ok を返します。それ以外の場合、エラー コード。</span><span class="sxs-lookup"><span data-stu-id="3ab21-109">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ab21-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ab21-110">See also</span></span>

- [<span data-ttu-id="3ab21-111">ISymUnmanagedDocument インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3ab21-111">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
