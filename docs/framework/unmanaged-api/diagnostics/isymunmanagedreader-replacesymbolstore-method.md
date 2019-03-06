---
title: ISymUnmanagedReader::ReplaceSymbolStore メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.ReplaceSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::ReplaceSymbolStore
helpviewer_keywords:
- ReplaceSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::ReplaceSymbolStore method [.NET Framework debugging]
ms.assetid: 43257761-8cb1-4eaf-8fb5-1f3980cb66cd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1b863816bfb7ed1a5db1fa2234db224b01cb6c9e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481548"
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a><span data-ttu-id="d6713-102">ISymUnmanagedReader::ReplaceSymbolStore メソッド</span><span class="sxs-lookup"><span data-stu-id="d6713-102">ISymUnmanagedReader::ReplaceSymbolStore Method</span></span>
<span data-ttu-id="d6713-103">既存のシンボル ストアをデルタ シンボル ストアで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="d6713-103">Replaces the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="d6713-104">このメソッドは、 [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)メソッドが、指定のデルタは、更新プログラムではなく、完全な置き換えとして機能します。</span><span class="sxs-lookup"><span data-stu-id="d6713-104">This method is similar to the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method, except that the given delta acts as a complete replacement rather than an update.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6713-105">いずれかのみを指定する必要があります、`filename`または`pIStream`両方のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="d6713-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="d6713-106">場合`filename`を指定すると、シンボル ストアはそのファイル内のシンボルで更新されます。</span><span class="sxs-lookup"><span data-stu-id="d6713-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="d6713-107">場合`pIStream`を指定すると、ストアからのデータで更新されます、<xref:System.Runtime.InteropServices.ComTypes.IStream>します。</span><span class="sxs-lookup"><span data-stu-id="d6713-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6713-108">構文</span><span class="sxs-lookup"><span data-stu-id="d6713-108">Syntax</span></span>  
  
```  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6713-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d6713-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="d6713-110">[in]シンボル ストアを含むファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="d6713-110">[in] The name of the file containing the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="d6713-111">[in]使用する代わりに、ファイル ストリーム、`filename`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="d6713-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d6713-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="d6713-112">Return Value</span></span>  
 <span data-ttu-id="d6713-113">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="d6713-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6713-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="d6713-114">Requirements</span></span>  
 <span data-ttu-id="d6713-115">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d6713-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6713-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6713-116">See also</span></span>
- [<span data-ttu-id="d6713-117">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d6713-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
