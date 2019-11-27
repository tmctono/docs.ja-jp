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
ms.openlocfilehash: 60c3537a80c39f758f46e6f2f0a5f2bcd27350b5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445736"
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a><span data-ttu-id="98f06-102">ISymUnmanagedReader::ReplaceSymbolStore メソッド</span><span class="sxs-lookup"><span data-stu-id="98f06-102">ISymUnmanagedReader::ReplaceSymbolStore Method</span></span>
<span data-ttu-id="98f06-103">既存のシンボル ストアをデルタ シンボル ストアで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="98f06-103">Replaces the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="98f06-104">このメソッドは、指定されたデルタが更新ではなく完全な置換として機能する点を除いて、"更新プログラム"[ストア](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)メソッドに似ています。</span><span class="sxs-lookup"><span data-stu-id="98f06-104">This method is similar to the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method, except that the given delta acts as a complete replacement rather than an update.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="98f06-105">両方ではなく、`filename` または `pIStream` のパラメーターのいずれか1つだけを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98f06-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="98f06-106">`filename` が指定されている場合、シンボルストアはそのファイル内のシンボルで更新されます。</span><span class="sxs-lookup"><span data-stu-id="98f06-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="98f06-107">`pIStream` が指定されている場合、ストアは <xref:System.Runtime.InteropServices.ComTypes.IStream>からのデータで更新されます。</span><span class="sxs-lookup"><span data-stu-id="98f06-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98f06-108">構文</span><span class="sxs-lookup"><span data-stu-id="98f06-108">Syntax</span></span>  
  
```cpp  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98f06-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="98f06-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="98f06-110">からシンボルストアを格納しているファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="98f06-110">[in] The name of the file containing the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="98f06-111">から`filename` パラメーターの代わりに使用されるファイルストリーム。</span><span class="sxs-lookup"><span data-stu-id="98f06-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="98f06-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="98f06-112">Return Value</span></span>  
 <span data-ttu-id="98f06-113">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="98f06-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98f06-114">要件</span><span class="sxs-lookup"><span data-stu-id="98f06-114">Requirements</span></span>  
 <span data-ttu-id="98f06-115">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="98f06-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98f06-116">参照</span><span class="sxs-lookup"><span data-stu-id="98f06-116">See also</span></span>

- [<span data-ttu-id="98f06-117">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="98f06-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
