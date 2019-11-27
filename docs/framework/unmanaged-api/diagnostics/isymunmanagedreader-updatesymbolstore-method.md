---
title: ISymUnmanagedReader::UpdateSymbolStore メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.UpdateSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::UpdateSymbolStore
helpviewer_keywords:
- UpdateSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::UpdateSymbolStore method [.NET Framework debugging]
ms.assetid: 4a17d723-86b9-4f27-bd0d-b70c3259011c
topic_type:
- apiref
ms.openlocfilehash: e052d9b7b2abd57b176dfe3b00afac626d422c58
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446461"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a><span data-ttu-id="76897-102">ISymUnmanagedReader::UpdateSymbolStore メソッド</span><span class="sxs-lookup"><span data-stu-id="76897-102">ISymUnmanagedReader::UpdateSymbolStore Method</span></span>
<span data-ttu-id="76897-103">既存のシンボル ストアをデルタ シンボル ストアで更新します。</span><span class="sxs-lookup"><span data-stu-id="76897-103">Updates the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="76897-104">このメソッドは、元のポータブル実行可能 (PE) ファイルにデルタを一致するようにシンボルストアを更新するために、エディットコンティニュシナリオで使用されます。</span><span class="sxs-lookup"><span data-stu-id="76897-104">This method is used in edit-and-continue scenarios to update the symbol store to match deltas to the original portable executable (PE) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="76897-105">両方ではなく、`filename` または `pIStream` のパラメーターのいずれか1つだけを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="76897-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="76897-106">`filename` が指定されている場合、シンボルストアはそのファイル内のシンボルで更新されます。</span><span class="sxs-lookup"><span data-stu-id="76897-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="76897-107">`pIStream` が指定されている場合、ストアは <xref:System.Runtime.InteropServices.ComTypes.IStream>からのデータで更新されます。</span><span class="sxs-lookup"><span data-stu-id="76897-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76897-108">構文</span><span class="sxs-lookup"><span data-stu-id="76897-108">Syntax</span></span>  
  
```cpp  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76897-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="76897-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="76897-110">からシンボルストアが格納されているファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="76897-110">[in] The name of the file that contains the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="76897-111">から`filename` パラメーターの代わりに使用されるファイルストリーム。</span><span class="sxs-lookup"><span data-stu-id="76897-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76897-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="76897-112">Return Value</span></span>  
 <span data-ttu-id="76897-113">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="76897-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76897-114">要件</span><span class="sxs-lookup"><span data-stu-id="76897-114">Requirements</span></span>  
 <span data-ttu-id="76897-115">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="76897-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76897-116">参照</span><span class="sxs-lookup"><span data-stu-id="76897-116">See also</span></span>

- [<span data-ttu-id="76897-117">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="76897-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
