---
title: ISymUnmanagedDocument インターフェイス
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument
helpviewer_keywords:
- ISymUnmanagedDocument interface [.NET Framework debugging]
ms.assetid: 5c26b366-6e81-467c-9dd0-02dd26fee0a3
topic_type:
- apiref
ms.openlocfilehash: a8ff6d3a925773e58e0713a87b167420c246f85b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615567"
---
# <a name="isymunmanageddocument-interface"></a><span data-ttu-id="e4865-102">ISymUnmanagedDocument インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e4865-102">ISymUnmanagedDocument Interface</span></span>
<span data-ttu-id="e4865-103">シンボル ストアによって参照されるドキュメントを表します。</span><span class="sxs-lookup"><span data-stu-id="e4865-103">Represents a document referenced by a symbol store.</span></span> <span data-ttu-id="e4865-104">ドキュメントは、URL (uniform resource locator) とドキュメントの種類の GUID によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="e4865-104">A document is defined by a uniform resource locator (URL) and a document type GUID.</span></span> <span data-ttu-id="e4865-105">URL とドキュメントの種類の GUID を使用して、ドキュメントがどのように格納されているかに関係なく、ドキュメントを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="e4865-105">You can locate the document regardless of how it is stored by using the URL and document type GUID.</span></span> <span data-ttu-id="e4865-106">ドキュメントソースをシンボルストアに格納し、このインターフェイスを使用して取得することができます。</span><span class="sxs-lookup"><span data-stu-id="e4865-106">You can store the document source in the symbol store and retrieve it through this interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e4865-107">メソッド</span><span class="sxs-lookup"><span data-stu-id="e4865-107">Methods</span></span>  
  
|<span data-ttu-id="e4865-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="e4865-108">Method</span></span>|<span data-ttu-id="e4865-109">説明</span><span class="sxs-lookup"><span data-stu-id="e4865-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e4865-110">FindClosestLine メソッド</span><span class="sxs-lookup"><span data-stu-id="e4865-110">FindClosestLine Method</span></span>](isymunmanageddocument-findclosestline-method.md)|<span data-ttu-id="e4865-111">このドキュメント内の行が指定されている場合は、シーケンスポイントで最も近い行を返します。</span><span class="sxs-lookup"><span data-stu-id="e4865-111">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>|  
|[<span data-ttu-id="e4865-112">GetCheckSum メソッド</span><span class="sxs-lookup"><span data-stu-id="e4865-112">GetCheckSum Method</span></span>](isymunmanageddocument-getchecksum-method.md)|<span data-ttu-id="e4865-113">チェックサムを取得します。</span><span class="sxs-lookup"><span data-stu-id="e4865-113">Gets the checksum.</span></span>|  
|[<span data-ttu-id="e4865-114">GetCheckSumAlgorithmId メソッド</span><span class="sxs-lookup"><span data-stu-id="e4865-114">GetCheckSumAlgorithmId Method</span></span>](isymunmanageddocument-getchecksumalgorithmid-method.md)|<span data-ttu-id="e4865-115">チェックサムアルゴリズム識別子を取得します。チェックサムがない場合は、すべての0の GUID を返します。</span><span class="sxs-lookup"><span data-stu-id="e4865-115">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>|  
|[<span data-ttu-id="e4865-116">GetDocumentType メソッド</span><span class="sxs-lookup"><span data-stu-id="e4865-116">GetDocumentType Method</span></span>](isymunmanageddocument-getdocumenttype-method.md)|<span data-ttu-id="e4865-117">このドキュメントのドキュメントの種類を取得します。</span><span class="sxs-lookup"><span data-stu-id="e4865-117">Gets the document type of this document.</span></span>|  
|[<span data-ttu-id="e4865-118">GetLanguage メソッド</span><span class="sxs-lookup"><span data-stu-id="e4865-118">GetLanguage Method</span></span>](isymunmanageddocument-getlanguage-method.md)|<span data-ttu-id="e4865-119">このドキュメントの言語識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="e4865-119">Gets the language identifier of this document.</span></span>|  
|[<span data-ttu-id="e4865-120">GetLanguageVendor メソッド</span><span class="sxs-lookup"><span data-stu-id="e4865-120">GetLanguageVendor Method</span></span>](isymunmanageddocument-getlanguagevendor-method.md)|<span data-ttu-id="e4865-121">このドキュメントの言語販売元を取得します。</span><span class="sxs-lookup"><span data-stu-id="e4865-121">Gets the language vendor of this document.</span></span>|  
|[<span data-ttu-id="e4865-122">GetSourceLength メソッド</span><span class="sxs-lookup"><span data-stu-id="e4865-122">GetSourceLength Method</span></span>](isymunmanageddocument-getsourcelength-method.md)|<span data-ttu-id="e4865-123">埋め込まれたソースの長さをバイト数で取得します。</span><span class="sxs-lookup"><span data-stu-id="e4865-123">Gets the length, in bytes, of the embedded source.</span></span>|  
|[<span data-ttu-id="e4865-124">GetSourceRange メソッド</span><span class="sxs-lookup"><span data-stu-id="e4865-124">GetSourceRange Method</span></span>](isymunmanageddocument-getsourcerange-method.md)|<span data-ttu-id="e4865-125">指定されたバッファーに、埋め込みソースの指定された範囲を返します。</span><span class="sxs-lookup"><span data-stu-id="e4865-125">Returns the specified range of the embedded source into the given buffer.</span></span>|  
|[<span data-ttu-id="e4865-126">GetURL メソッド</span><span class="sxs-lookup"><span data-stu-id="e4865-126">GetURL Method</span></span>](isymunmanageddocument-geturl-method.md)|<span data-ttu-id="e4865-127">このドキュメントの URL を返します。</span><span class="sxs-lookup"><span data-stu-id="e4865-127">Returns the URL for this document.</span></span>|  
|[<span data-ttu-id="e4865-128">HasEmbeddedSource メソッド</span><span class="sxs-lookup"><span data-stu-id="e4865-128">HasEmbeddedSource Method</span></span>](isymunmanageddocument-hasembeddedsource-method.md)|<span data-ttu-id="e4865-129">`true`ドキュメントがデバッグシンボルに埋め込まれている場合はを返します。それ以外の場合はを返し `false` ます。</span><span class="sxs-lookup"><span data-stu-id="e4865-129">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e4865-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="e4865-130">See also</span></span>

- [<span data-ttu-id="e4865-131">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e4865-131">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
