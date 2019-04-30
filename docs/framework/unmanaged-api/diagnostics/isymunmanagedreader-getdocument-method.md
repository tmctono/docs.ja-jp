---
title: ISymUnmanagedReader::GetDocument メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocument
helpviewer_keywords:
- ISymUnmanagedReader::GetDocument method [.NET Framework debugging]
- GetDocument method [.NET Framework debugging]
ms.assetid: bb203853-6a6d-4027-b9e9-603a7f28b9d3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2a173c23ea33532f05e30d072677715e15d04018
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939478"
---
# <a name="isymunmanagedreadergetdocument-method"></a><span data-ttu-id="fc717-102">ISymUnmanagedReader::GetDocument メソッド</span><span class="sxs-lookup"><span data-stu-id="fc717-102">ISymUnmanagedReader::GetDocument Method</span></span>
<span data-ttu-id="fc717-103">ドキュメントを検索します。</span><span class="sxs-lookup"><span data-stu-id="fc717-103">Finds a document.</span></span> <span data-ttu-id="fc717-104">ドキュメントの言語、ベンダー、および種類は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="fc717-104">The document language, vendor, and type are optional.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc717-105">構文</span><span class="sxs-lookup"><span data-stu-id="fc717-105">Syntax</span></span>  
  
```  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc717-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fc717-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="fc717-107">[in]ドキュメントを識別する URL です。</span><span class="sxs-lookup"><span data-stu-id="fc717-107">[in] The URL that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="fc717-108">[in]ドキュメントの言語。</span><span class="sxs-lookup"><span data-stu-id="fc717-108">[in] The document language.</span></span> <span data-ttu-id="fc717-109">このパラメーターは省略できます。</span><span class="sxs-lookup"><span data-stu-id="fc717-109">This parameter is optional.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="fc717-110">[in]ドキュメントの言語のベンダーの id。</span><span class="sxs-lookup"><span data-stu-id="fc717-110">[in] The identity of the vendor for the document language.</span></span> <span data-ttu-id="fc717-111">このパラメーターは省略できます。</span><span class="sxs-lookup"><span data-stu-id="fc717-111">This parameter is optional.</span></span>  
  
 `documentType`  
 <span data-ttu-id="fc717-112">[in]ドキュメントの種類。</span><span class="sxs-lookup"><span data-stu-id="fc717-112">[in] The type of the document.</span></span> <span data-ttu-id="fc717-113">このパラメーターは省略できます。</span><span class="sxs-lookup"><span data-stu-id="fc717-113">This parameter is optional.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="fc717-114">[out]返されたインターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="fc717-114">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fc717-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="fc717-115">Return Value</span></span>  
 <span data-ttu-id="fc717-116">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="fc717-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc717-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="fc717-117">Requirements</span></span>  
 <span data-ttu-id="fc717-118">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fc717-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc717-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="fc717-119">See also</span></span>

- [<span data-ttu-id="fc717-120">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fc717-120">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
