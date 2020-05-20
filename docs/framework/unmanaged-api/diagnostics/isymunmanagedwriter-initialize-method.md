---
title: ISymUnmanagedWriter::Initialize メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: e0ebd793-3764-4df0-8f12-0e95f60b9eae
topic_type:
- apiref
ms.openlocfilehash: 1553e616f60b4f05c06b6457d47454dfb4bc2eb7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614774"
---
# <a name="isymunmanagedwriterinitialize-method"></a><span data-ttu-id="6db75-102">ISymUnmanagedWriter::Initialize メソッド</span><span class="sxs-lookup"><span data-stu-id="6db75-102">ISymUnmanagedWriter::Initialize Method</span></span>
<span data-ttu-id="6db75-103">このライターが関連付けられるメタデータエミッタインターフェイスを設定し、デバッグシンボルの書き込み先となる出力ファイル名を設定します。</span><span class="sxs-lookup"><span data-stu-id="6db75-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span>  
  
 <span data-ttu-id="6db75-104">このメソッドを呼び出すことができるのは1回だけです。他のライターメソッドの前に呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="6db75-104">This method can be called only once, and it must be called before any other writer methods.</span></span> <span data-ttu-id="6db75-105">一部のライターでは、ファイル名が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6db75-105">Some writers may require a file name.</span></span> <span data-ttu-id="6db75-106">ただし、ファイル名を使用しないライターに悪影響を及ぼすことなく、常にファイル名をこのメソッドに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="6db75-106">However, you can always pass a file name to this method without any negative effect on writers that do not use the file name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6db75-107">構文</span><span class="sxs-lookup"><span data-stu-id="6db75-107">Syntax</span></span>  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *filename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6db75-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6db75-108">Parameters</span></span>  
 `emitter`  
 <span data-ttu-id="6db75-109">からメタデータエミッタインターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6db75-109">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `filename`  
 <span data-ttu-id="6db75-110">からデバッグシンボルが書き込まれるファイル名。</span><span class="sxs-lookup"><span data-stu-id="6db75-110">[in] The file name to which the debugging symbols are written.</span></span> <span data-ttu-id="6db75-111">ファイル名を使用しないライターに対してファイル名を指定した場合、このパラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="6db75-111">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="6db75-112">から指定した場合、シンボルライターは、パラメーターで指定されたファイルではなく、指定されたにシンボルを出力し <xref:System.Runtime.InteropServices.ComTypes.IStream> `filename` ます。</span><span class="sxs-lookup"><span data-stu-id="6db75-112">[in] If specified, the symbol writer will emit the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="6db75-113">`pIStream` パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="6db75-113">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="6db75-114">[入力] `true`完全な再構築の場合は、`false`インクリメンタルコンパイルの場合は。</span><span class="sxs-lookup"><span data-stu-id="6db75-114">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6db75-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="6db75-115">Return Value</span></span>  
 <span data-ttu-id="6db75-116">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="6db75-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6db75-117">要件</span><span class="sxs-lookup"><span data-stu-id="6db75-117">Requirements</span></span>  
 <span data-ttu-id="6db75-118">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="6db75-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6db75-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="6db75-119">See also</span></span>

- [<span data-ttu-id="6db75-120">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6db75-120">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="6db75-121">Initialize2 メソッド</span><span class="sxs-lookup"><span data-stu-id="6db75-121">Initialize2 Method</span></span>](isymunmanagedwriter-initialize2-method.md)
