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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c1ea9424c000ad3ae4918181084c89038c2ec8d1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777292"
---
# <a name="isymunmanagedwriterinitialize-method"></a><span data-ttu-id="e66bd-102">ISymUnmanagedWriter::Initialize メソッド</span><span class="sxs-lookup"><span data-stu-id="e66bd-102">ISymUnmanagedWriter::Initialize Method</span></span>
<span data-ttu-id="e66bd-103">このライターが関連付けられるメタデータ エミッタ インターフェイスを設定し、デバッグ シンボルが書き込まれる出力ファイル名を設定します。</span><span class="sxs-lookup"><span data-stu-id="e66bd-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span>  
  
 <span data-ttu-id="e66bd-104">このメソッドは、1 回だけ呼び出すことができ、他のライター メソッドの前に、呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="e66bd-104">This method can be called only once, and it must be called before any other writer methods.</span></span> <span data-ttu-id="e66bd-105">一部の開発者には、ファイル名が必要です。</span><span class="sxs-lookup"><span data-stu-id="e66bd-105">Some writers may require a file name.</span></span> <span data-ttu-id="e66bd-106">ただし、ファイル名には、ファイル名を使用しないライターに、悪影響を及ぼすことがなく、このメソッドに常に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="e66bd-106">However, you can always pass a file name to this method without any negative effect on writers that do not use the file name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e66bd-107">構文</span><span class="sxs-lookup"><span data-stu-id="e66bd-107">Syntax</span></span>  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *filename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e66bd-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e66bd-108">Parameters</span></span>  
 `emitter`  
 <span data-ttu-id="e66bd-109">[in]メタデータ エミッタ インターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e66bd-109">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `filename`  
 <span data-ttu-id="e66bd-110">[in]デバッグ シンボルが書き込まれるファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="e66bd-110">[in] The file name to which the debugging symbols are written.</span></span> <span data-ttu-id="e66bd-111">ファイル名を使用しないライターに対してファイル名を指定した場合、このパラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="e66bd-111">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="e66bd-112">[in]シンボルのライターにシンボルを出力、指定されている場合、指定された<xref:System.Runtime.InteropServices.ComTypes.IStream>で指定されたファイルではなく、`filename`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="e66bd-112">[in] If specified, the symbol writer will emit the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="e66bd-113">`pIStream` パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e66bd-113">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="e66bd-114">[in]`true`場合、これは、完全な再構築します。`false`インクリメンタル コンパイルの場合。</span><span class="sxs-lookup"><span data-stu-id="e66bd-114">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e66bd-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="e66bd-115">Return Value</span></span>  
 <span data-ttu-id="e66bd-116">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="e66bd-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e66bd-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="e66bd-117">Requirements</span></span>  
 <span data-ttu-id="e66bd-118">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e66bd-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e66bd-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="e66bd-119">See also</span></span>

- [<span data-ttu-id="e66bd-120">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e66bd-120">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="e66bd-121">Initialize2 メソッド</span><span class="sxs-lookup"><span data-stu-id="e66bd-121">Initialize2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)
