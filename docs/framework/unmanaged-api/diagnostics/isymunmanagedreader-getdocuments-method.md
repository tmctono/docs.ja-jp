---
title: ISymUnmanagedReader::GetDocuments メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocuments
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocuments
helpviewer_keywords:
- GetDocuments method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocuments method [.NET Framework debugging]
ms.assetid: e3b73a3f-d089-4101-a9a9-5e0765d05b61
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: efcf5b6673fbdc37fad99d082f91ab3077abbea9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130599"
---
# <a name="isymunmanagedreadergetdocuments-method"></a><span data-ttu-id="1ed9f-102">ISymUnmanagedReader::GetDocuments メソッド</span><span class="sxs-lookup"><span data-stu-id="1ed9f-102">ISymUnmanagedReader::GetDocuments Method</span></span>
<span data-ttu-id="1ed9f-103">シンボル ストアで定義されているすべてのドキュメントの配列を返します。</span><span class="sxs-lookup"><span data-stu-id="1ed9f-103">Returns an array of all the documents defined in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ed9f-104">構文</span><span class="sxs-lookup"><span data-stu-id="1ed9f-104">Syntax</span></span>  
  
```  
HRESULT GetDocuments (  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,  
    [out, size_is (cDocs),  
        length_is (*pcDocs)] ISymUnmanagedDocument *pDocs[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ed9f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1ed9f-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="1ed9f-106">[in] `pDocs` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="1ed9f-106">[in] The size of the `pDocs` array.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="1ed9f-107">[out]配列の長さを受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="1ed9f-107">[out] A pointer to a variable that receives the array length.</span></span>  
  
 `pDocs`  
 <span data-ttu-id="1ed9f-108">[out]ドキュメントの配列を受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="1ed9f-108">[out] A pointer to a variable that receives the document array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ed9f-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="1ed9f-109">Return Value</span></span>  
 <span data-ttu-id="1ed9f-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="1ed9f-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ed9f-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="1ed9f-111">Requirements</span></span>  
 <span data-ttu-id="1ed9f-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1ed9f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ed9f-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ed9f-113">See also</span></span>

- [<span data-ttu-id="1ed9f-114">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1ed9f-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
