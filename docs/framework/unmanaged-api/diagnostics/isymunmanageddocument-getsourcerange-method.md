---
title: ISymUnmanagedDocument::GetSourceRange メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceRange
helpviewer_keywords:
- ISymUnmanagedDocument::GetSourceRange method [.NET Framework debugging]
- GetSourceRange method [.NET Framework debugging]
ms.assetid: 20fefee7-1040-41ba-93dc-bd42f68b90c2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 767508e51660a161a7a6ff0b168a46178d66be99
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474147"
---
# <a name="isymunmanageddocumentgetsourcerange-method"></a><span data-ttu-id="fdc41-102">ISymUnmanagedDocument::GetSourceRange メソッド</span><span class="sxs-lookup"><span data-stu-id="fdc41-102">ISymUnmanagedDocument::GetSourceRange Method</span></span>
<span data-ttu-id="fdc41-103">指定されたバッファーに埋め込みのソースの指定した範囲を返します。</span><span class="sxs-lookup"><span data-stu-id="fdc41-103">Returns the specified range of the embedded source into the given buffer.</span></span> <span data-ttu-id="fdc41-104">バッファーは、ソースを保持するために十分な大きさである必要があります。</span><span class="sxs-lookup"><span data-stu-id="fdc41-104">The buffer must be large enough to hold the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdc41-105">構文</span><span class="sxs-lookup"><span data-stu-id="fdc41-105">Syntax</span></span>  
  
```  
HRESULT GetSourceRange(  
    [in]  ULONG32  startLine,  
    [in]  ULONG32  startColumn,  
    [in]  ULONG32  endLine,  
    [in]  ULONG32  endColumn,  
    [in]  ULONG32  cSourceBytes,  
    [out] ULONG32  *pcSourceBytes,  
    [out, size_is(cSourceBytes),  
        length_is(*pcSourceBytes)] BYTE source[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fdc41-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fdc41-106">Parameters</span></span>  
 `startLine`  
 <span data-ttu-id="fdc41-107">[in]現在のドキュメント内の開始行。</span><span class="sxs-lookup"><span data-stu-id="fdc41-107">[in] The starting line in the current document.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="fdc41-108">[in]現在のドキュメント内の開始列。</span><span class="sxs-lookup"><span data-stu-id="fdc41-108">[in] The starting column in the current document.</span></span>  
  
 `endLine`  
 <span data-ttu-id="fdc41-109">[in]現在のドキュメントの最後の行。</span><span class="sxs-lookup"><span data-stu-id="fdc41-109">[in] The final line in the current document.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="fdc41-110">[in]現在のドキュメントの最後の列。</span><span class="sxs-lookup"><span data-stu-id="fdc41-110">[in] The final column in the current document.</span></span>  
  
 `cSourceBytes`  
 <span data-ttu-id="fdc41-111">[in] \(バイト単位)、ソースのサイズ。</span><span class="sxs-lookup"><span data-stu-id="fdc41-111">[in] The size of the source, in bytes.</span></span>  
  
 `pcSourceBytes`  
 <span data-ttu-id="fdc41-112">[out]ソースのサイズを受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="fdc41-112">[out] A pointer to a variable that receives the source size.</span></span>  
  
 `source`  
 <span data-ttu-id="fdc41-113">[out]サイズと指定されたバイト数で、ソース ドキュメントの範囲の長さ。</span><span class="sxs-lookup"><span data-stu-id="fdc41-113">[out] The size and length of the specified range of the source document, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fdc41-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="fdc41-114">Return Value</span></span>  
 <span data-ttu-id="fdc41-115">メソッドが成功した場合は s_ok を返します。</span><span class="sxs-lookup"><span data-stu-id="fdc41-115">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdc41-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="fdc41-116">See also</span></span>
- [<span data-ttu-id="fdc41-117">ISymUnmanagedDocument インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fdc41-117">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
