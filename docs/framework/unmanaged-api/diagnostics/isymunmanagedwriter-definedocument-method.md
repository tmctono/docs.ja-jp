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
ms.openlocfilehash: 02b270677131d0960db67b0ac8db38cba2b5e2df
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428045"
---
# <a name="isymunmanagedwriterdefinedocument-method"></a><span data-ttu-id="a940e-102">ISymUnmanagedWriter::DefineDocument メソッド</span><span class="sxs-lookup"><span data-stu-id="a940e-102">ISymUnmanagedWriter::DefineDocument Method</span></span>
<span data-ttu-id="a940e-103">ソース ドキュメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="a940e-103">Defines a source document.</span></span> <span data-ttu-id="a940e-104">Guid は、既知の言語、ベンダー、およびドキュメントの種類に対して提供されます。</span><span class="sxs-lookup"><span data-stu-id="a940e-104">GUIDs are provided for known languages, vendors, and document types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a940e-105">構文</span><span class="sxs-lookup"><span data-stu-id="a940e-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a940e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a940e-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="a940e-107">からドキュメントを識別する URL (uniform resource locator) を定義する `WCHAR` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="a940e-107">[in] A pointer to a `WCHAR` that defines the uniform resource locator (URL) that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="a940e-108">からドキュメントの言語を定義する GUID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="a940e-108">[in] A pointer to a GUID that defines the document language.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="a940e-109">からドキュメント言語のベンダの id を定義する GUID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="a940e-109">[in] A pointer to a GUID that defines the identity of the vendor for the document language.</span></span>  
  
 `documentType`  
 <span data-ttu-id="a940e-110">からドキュメントの種類を定義する GUID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="a940e-110">[in] A pointer to a GUID that defines the type of the document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="a940e-111">入出力返された[ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)インターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a940e-111">[out] A pointer to the returned [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a940e-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="a940e-112">Return Value</span></span>  
 <span data-ttu-id="a940e-113">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="a940e-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a940e-114">要件</span><span class="sxs-lookup"><span data-stu-id="a940e-114">Requirements</span></span>  
 <span data-ttu-id="a940e-115">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="a940e-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a940e-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="a940e-116">See also</span></span>

- [<span data-ttu-id="a940e-117">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a940e-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
