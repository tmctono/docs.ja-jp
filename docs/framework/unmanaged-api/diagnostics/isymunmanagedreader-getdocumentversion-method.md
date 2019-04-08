---
title: ISymUnmanagedReader::GetDocumentVersion メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocumentVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocumentVersion
helpviewer_keywords:
- GetDocumentVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocumentVersion method [.NET Framework debugging]
ms.assetid: a51f1f64-e084-44c5-830c-2222da5a6bbf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 92353cfc2d9ce39074bf43937b5673ff51e34822
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080008"
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a><span data-ttu-id="1dda2-102">ISymUnmanagedReader::GetDocumentVersion メソッド</span><span class="sxs-lookup"><span data-stu-id="1dda2-102">ISymUnmanagedReader::GetDocumentVersion Method</span></span>
<span data-ttu-id="1dda2-103">指定されたドキュメントの指定したバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="1dda2-103">Gets the specified version of the specified document.</span></span> <span data-ttu-id="1dda2-104">ドキュメントのバージョンが 1 から始まりを使用して、ドキュメントが更新されるたびに増分されますが、 [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="1dda2-104">The document version starts at 1 and is incremented each time the document is updated using the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method.</span></span> <span data-ttu-id="1dda2-105">場合、`pbCurrent`パラメーターが`true`、これは、ドキュメントの最新バージョンです。</span><span class="sxs-lookup"><span data-stu-id="1dda2-105">If the `pbCurrent` parameter is `true`, this is the latest version of the document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dda2-106">構文</span><span class="sxs-lookup"><span data-stu-id="1dda2-106">Syntax</span></span>  
  
```  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1dda2-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1dda2-107">Parameters</span></span>  
 `pDoc`  
 <span data-ttu-id="1dda2-108">[in]指定されたドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="1dda2-108">[in] The specified document.</span></span>  
  
 `version`  
 <span data-ttu-id="1dda2-109">[out]指定されたドキュメントのバージョンを受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="1dda2-109">[out] A pointer to a variable that receives the version of the specified document.</span></span>  
  
 `pbCurrent`  
 <span data-ttu-id="1dda2-110">[out]受け取る変数へのポインター`true`場合、これは、ドキュメントの最新バージョンまたは`false`最新のバージョンでない場合。</span><span class="sxs-lookup"><span data-stu-id="1dda2-110">[out] A pointer to a variable that receives `true` if this is the latest version of the document, or `false` if it isn't the latest version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1dda2-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="1dda2-111">Return Value</span></span>  
 <span data-ttu-id="1dda2-112">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="1dda2-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1dda2-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="1dda2-113">Requirements</span></span>  
 <span data-ttu-id="1dda2-114">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1dda2-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dda2-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="1dda2-115">See also</span></span>

- [<span data-ttu-id="1dda2-116">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1dda2-116">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
