---
title: ISymUnmanagedWriter::DefineDocument メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineDocument
helpviewer_keywords:
- ISymUnmanagedWriter::DefineDocument method [.NET Framework debugging]
- DefineDocument method [.NET Framework debugging]
ms.assetid: c3bf15b0-3250-4bbe-b9b5-c5d695289b6f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 726ac0e23f739f451e1a0ab66c4c36aa6edbe569
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132133"
---
# <a name="isymunmanagedwriterdefinedocument-method"></a><span data-ttu-id="87d58-102">ISymUnmanagedWriter::DefineDocument メソッド</span><span class="sxs-lookup"><span data-stu-id="87d58-102">ISymUnmanagedWriter::DefineDocument Method</span></span>
<span data-ttu-id="87d58-103">ソース ドキュメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="87d58-103">Defines a source document.</span></span> <span data-ttu-id="87d58-104">既知の言語、ベンダー、およびドキュメントの種類の Guid が提供されます。</span><span class="sxs-lookup"><span data-stu-id="87d58-104">GUIDs are provided for known languages, vendors, and document types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87d58-105">構文</span><span class="sxs-lookup"><span data-stu-id="87d58-105">Syntax</span></span>  
  
```  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87d58-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="87d58-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="87d58-107">[in]ポインター、`WCHAR`ドキュメントを識別する uniform resource locator (URL) を定義します。</span><span class="sxs-lookup"><span data-stu-id="87d58-107">[in] A pointer to a `WCHAR` that defines the uniform resource locator (URL) that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="87d58-108">[in]ドキュメントの言語を定義する GUID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="87d58-108">[in] A pointer to a GUID that defines the document language.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="87d58-109">[in]ドキュメントの言語のベンダーの id を定義する GUID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="87d58-109">[in] A pointer to a GUID that defines the identity of the vendor for the document language.</span></span>  
  
 `documentType`  
 <span data-ttu-id="87d58-110">[in]ドキュメントの種類を定義する GUID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="87d58-110">[in] A pointer to a GUID that defines the type of the document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="87d58-111">[out]返されたポインター [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="87d58-111">[out] A pointer to the returned [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87d58-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="87d58-112">Return Value</span></span>  
 <span data-ttu-id="87d58-113">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="87d58-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87d58-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="87d58-114">Requirements</span></span>  
 <span data-ttu-id="87d58-115">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="87d58-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87d58-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="87d58-116">See also</span></span>

- [<span data-ttu-id="87d58-117">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="87d58-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
