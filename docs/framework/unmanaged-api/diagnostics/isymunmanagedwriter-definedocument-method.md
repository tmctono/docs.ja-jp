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
ms.openlocfilehash: fdcfb0c4f9c21eb516f4196d0c8f682669468219
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615229"
---
# <a name="isymunmanagedwriterdefinedocument-method"></a><span data-ttu-id="5b4c2-102">ISymUnmanagedWriter::DefineDocument メソッド</span><span class="sxs-lookup"><span data-stu-id="5b4c2-102">ISymUnmanagedWriter::DefineDocument Method</span></span>
<span data-ttu-id="5b4c2-103">ソース ドキュメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="5b4c2-103">Defines a source document.</span></span> <span data-ttu-id="5b4c2-104">Guid は、既知の言語、ベンダー、およびドキュメントの種類に対して提供されます。</span><span class="sxs-lookup"><span data-stu-id="5b4c2-104">GUIDs are provided for known languages, vendors, and document types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b4c2-105">構文</span><span class="sxs-lookup"><span data-stu-id="5b4c2-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b4c2-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5b4c2-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="5b4c2-107">から`WCHAR`ドキュメントを識別する URL (uniform resource locator) を定義するへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5b4c2-107">[in] A pointer to a `WCHAR` that defines the uniform resource locator (URL) that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="5b4c2-108">からドキュメントの言語を定義する GUID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="5b4c2-108">[in] A pointer to a GUID that defines the document language.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="5b4c2-109">からドキュメント言語のベンダの id を定義する GUID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="5b4c2-109">[in] A pointer to a GUID that defines the identity of the vendor for the document language.</span></span>  
  
 `documentType`  
 <span data-ttu-id="5b4c2-110">からドキュメントの種類を定義する GUID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="5b4c2-110">[in] A pointer to a GUID that defines the type of the document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="5b4c2-111">入出力返された[ISymUnmanagedWriter](isymunmanagedwriter-interface.md)インターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5b4c2-111">[out] A pointer to the returned [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b4c2-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="5b4c2-112">Return Value</span></span>  
 <span data-ttu-id="5b4c2-113">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="5b4c2-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b4c2-114">要件</span><span class="sxs-lookup"><span data-stu-id="5b4c2-114">Requirements</span></span>  
 <span data-ttu-id="5b4c2-115">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="5b4c2-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b4c2-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b4c2-116">See also</span></span>

- [<span data-ttu-id="5b4c2-117">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5b4c2-117">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
