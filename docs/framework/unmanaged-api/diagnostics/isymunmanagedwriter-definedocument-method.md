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
ms.openlocfilehash: b9a36e094689696b746fcf7f10c282a1b0d9c570
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777839"
---
# <a name="isymunmanagedwriterdefinedocument-method"></a><span data-ttu-id="b5683-102">ISymUnmanagedWriter::DefineDocument メソッド</span><span class="sxs-lookup"><span data-stu-id="b5683-102">ISymUnmanagedWriter::DefineDocument Method</span></span>
<span data-ttu-id="b5683-103">ソース ドキュメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="b5683-103">Defines a source document.</span></span> <span data-ttu-id="b5683-104">既知の言語、ベンダー、およびドキュメントの種類の Guid が提供されます。</span><span class="sxs-lookup"><span data-stu-id="b5683-104">GUIDs are provided for known languages, vendors, and document types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5683-105">構文</span><span class="sxs-lookup"><span data-stu-id="b5683-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5683-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b5683-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="b5683-107">[in]ポインター、`WCHAR`ドキュメントを識別する uniform resource locator (URL) を定義します。</span><span class="sxs-lookup"><span data-stu-id="b5683-107">[in] A pointer to a `WCHAR` that defines the uniform resource locator (URL) that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="b5683-108">[in]ドキュメントの言語を定義する GUID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="b5683-108">[in] A pointer to a GUID that defines the document language.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="b5683-109">[in]ドキュメントの言語のベンダーの id を定義する GUID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="b5683-109">[in] A pointer to a GUID that defines the identity of the vendor for the document language.</span></span>  
  
 `documentType`  
 <span data-ttu-id="b5683-110">[in]ドキュメントの種類を定義する GUID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="b5683-110">[in] A pointer to a GUID that defines the type of the document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="b5683-111">[out]返されたポインター [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="b5683-111">[out] A pointer to the returned [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5683-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="b5683-112">Return Value</span></span>  
 <span data-ttu-id="b5683-113">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="b5683-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5683-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="b5683-114">Requirements</span></span>  
 <span data-ttu-id="b5683-115">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b5683-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5683-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5683-116">See also</span></span>

- [<span data-ttu-id="b5683-117">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b5683-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
