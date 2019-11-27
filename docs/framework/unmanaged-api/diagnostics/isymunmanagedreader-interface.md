---
title: ISymUnmanagedReader インターフェイス
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader
helpviewer_keywords:
- ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: aa3cc15d-058e-4e6f-b03e-39569646ba47
topic_type:
- apiref
ms.openlocfilehash: 7ae978f5d2c9f7e90f4549c15a3935b441eabf04
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434010"
---
# <a name="isymunmanagedreader-interface"></a><span data-ttu-id="d8d37-102">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d8d37-102">ISymUnmanagedReader Interface</span></span>
<span data-ttu-id="d8d37-103">シンボルストア内のドキュメント、メソッド、および変数へのアクセスを提供するシンボルリーダーを表します。</span><span class="sxs-lookup"><span data-stu-id="d8d37-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d8d37-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="d8d37-104">Methods</span></span>  
  
|<span data-ttu-id="d8d37-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="d8d37-105">Method</span></span>|<span data-ttu-id="d8d37-106">説明</span><span class="sxs-lookup"><span data-stu-id="d8d37-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d8d37-107">GetDocument メソッド</span><span class="sxs-lookup"><span data-stu-id="d8d37-107">GetDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocument-method.md)|<span data-ttu-id="d8d37-108">ドキュメントを検索します。</span><span class="sxs-lookup"><span data-stu-id="d8d37-108">Finds a document.</span></span>|  
|[<span data-ttu-id="d8d37-109">GetDocuments メソッド</span><span class="sxs-lookup"><span data-stu-id="d8d37-109">GetDocuments Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocuments-method.md)|<span data-ttu-id="d8d37-110">シンボルストアに定義されているすべてのドキュメントの配列を返します。</span><span class="sxs-lookup"><span data-stu-id="d8d37-110">Returns an array of all the documents defined in the symbol store.</span></span>|  
|[<span data-ttu-id="d8d37-111">GetDocumentVersion メソッド</span><span class="sxs-lookup"><span data-stu-id="d8d37-111">GetDocumentVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocumentversion-method.md)|<span data-ttu-id="d8d37-112">指定したドキュメントの指定したバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="d8d37-112">Gets the specified version of the specified document.</span></span>|  
|[<span data-ttu-id="d8d37-113">GetGlobalVariables メソッド</span><span class="sxs-lookup"><span data-stu-id="d8d37-113">GetGlobalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getglobalvariables-method.md)|<span data-ttu-id="d8d37-114">すべてのグローバル変数を返します。</span><span class="sxs-lookup"><span data-stu-id="d8d37-114">Returns all global variables.</span></span>|  
|[<span data-ttu-id="d8d37-115">GetMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="d8d37-115">GetMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethod-method.md)|<span data-ttu-id="d8d37-116">メソッドトークンを指定して、シンボルリーダーメソッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="d8d37-116">Gets a symbol reader method, given a method token.</span></span>|  
|[<span data-ttu-id="d8d37-117">GetMethodByVersion メソッド</span><span class="sxs-lookup"><span data-stu-id="d8d37-117">GetMethodByVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodbyversion-method.md)|<span data-ttu-id="d8d37-118">メソッドトークンと編集およびコピーバージョン番号を指定して、シンボルリーダーメソッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="d8d37-118">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span>|  
|[<span data-ttu-id="d8d37-119">GetMethodFromDocumentPosition メソッド</span><span class="sxs-lookup"><span data-stu-id="d8d37-119">GetMethodFromDocumentPosition Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodfromdocumentposition-method.md)|<span data-ttu-id="d8d37-120">ドキュメント内の指定された位置にあるブレークポイントを含むメソッドを返します。</span><span class="sxs-lookup"><span data-stu-id="d8d37-120">Returns the method that contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="d8d37-121">GetMethodsFromDocumentPosition メソッド</span><span class="sxs-lookup"><span data-stu-id="d8d37-121">GetMethodsFromDocumentPosition Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodsfromdocumentposition-method.md)|<span data-ttu-id="d8d37-122">メソッドの配列を返します。各メソッドには、ドキュメント内の指定された位置にあるブレークポイントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d8d37-122">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="d8d37-123">GetMethodVersion メソッド</span><span class="sxs-lookup"><span data-stu-id="d8d37-123">GetMethodVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodversion-method.md)|<span data-ttu-id="d8d37-124">メソッドのバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="d8d37-124">Gets the method version.</span></span>|  
|[<span data-ttu-id="d8d37-125">GetNamespaces メソッド</span><span class="sxs-lookup"><span data-stu-id="d8d37-125">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getnamespaces-method.md)|<span data-ttu-id="d8d37-126">このシンボルストア内のグローバルスコープで定義されている名前空間を取得します。</span><span class="sxs-lookup"><span data-stu-id="d8d37-126">Gets the namespaces defined at global scope within this symbol store.</span></span>|  
|[<span data-ttu-id="d8d37-127">GetSymAttribute メソッド</span><span class="sxs-lookup"><span data-stu-id="d8d37-127">GetSymAttribute Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymattribute-method.md)|<span data-ttu-id="d8d37-128">名前に基づいてカスタム属性を取得します。</span><span class="sxs-lookup"><span data-stu-id="d8d37-128">Gets a custom attribute based upon its name.</span></span>|  
|[<span data-ttu-id="d8d37-129">GetSymbolStoreFileName メソッド</span><span class="sxs-lookup"><span data-stu-id="d8d37-129">GetSymbolStoreFileName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymbolstorefilename-method.md)|<span data-ttu-id="d8d37-130">シンボルストアのディスク上のファイル名を提供します。</span><span class="sxs-lookup"><span data-stu-id="d8d37-130">Provides the on-disk file name of the symbol store.</span></span>|  
|[<span data-ttu-id="d8d37-131">GetUserEntryPoint メソッド</span><span class="sxs-lookup"><span data-stu-id="d8d37-131">GetUserEntryPoint Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getuserentrypoint-method.md)|<span data-ttu-id="d8d37-132">モジュールのユーザーエントリポイントとして指定されたメソッド (存在する場合) を返します。</span><span class="sxs-lookup"><span data-stu-id="d8d37-132">Returns the method that was specified as the user entry point for the module, if any.</span></span>|  
|[<span data-ttu-id="d8d37-133">GetVariables メソッド</span><span class="sxs-lookup"><span data-stu-id="d8d37-133">GetVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getvariables-method.md)|<span data-ttu-id="d8d37-134">親と名前を指定して、非ローカル変数を返します。</span><span class="sxs-lookup"><span data-stu-id="d8d37-134">Return a non-local variable, given its parent and name.</span></span>|  
|[<span data-ttu-id="d8d37-135">Initialize メソッド</span><span class="sxs-lookup"><span data-stu-id="d8d37-135">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-initialize-method.md)|<span data-ttu-id="d8d37-136">このリーダーが関連付けられるメタデータインポーターインターフェイスと、モジュールのファイル名を使用して、シンボルリーダーを初期化します。</span><span class="sxs-lookup"><span data-stu-id="d8d37-136">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>|  
|[<span data-ttu-id="d8d37-137">ReplaceSymbolStore メソッド</span><span class="sxs-lookup"><span data-stu-id="d8d37-137">ReplaceSymbolStore Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md)|<span data-ttu-id="d8d37-138">既存のシンボル ストアをデルタ シンボル ストアで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="d8d37-138">Replaces the existing symbol store with a delta symbol store.</span></span>|  
|[<span data-ttu-id="d8d37-139">UpdateSymbolStore メソッド</span><span class="sxs-lookup"><span data-stu-id="d8d37-139">UpdateSymbolStore Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)|<span data-ttu-id="d8d37-140">既存のシンボル ストアをデルタ シンボル ストアで更新します。</span><span class="sxs-lookup"><span data-stu-id="d8d37-140">Updates the existing symbol store with a delta symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d8d37-141">要件</span><span class="sxs-lookup"><span data-stu-id="d8d37-141">Requirements</span></span>  
 <span data-ttu-id="d8d37-142">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="d8d37-142">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8d37-143">参照</span><span class="sxs-lookup"><span data-stu-id="d8d37-143">See also</span></span>

- [<span data-ttu-id="d8d37-144">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d8d37-144">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="d8d37-145">ISymUnmanagedReader2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d8d37-145">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
