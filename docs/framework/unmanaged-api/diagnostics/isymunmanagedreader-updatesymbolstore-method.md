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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f62c954bf9d73ab564eba388e742794a330362d4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080502"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a><span data-ttu-id="c1583-102">ISymUnmanagedReader::UpdateSymbolStore メソッド</span><span class="sxs-lookup"><span data-stu-id="c1583-102">ISymUnmanagedReader::UpdateSymbolStore Method</span></span>
<span data-ttu-id="c1583-103">既存のシンボル ストアをデルタ シンボル ストアで更新します。</span><span class="sxs-lookup"><span data-stu-id="c1583-103">Updates the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="c1583-104">このメソッドは、元のポータブル実行可能 (PE) ファイルの差分を一致するように、シンボル ストアを更新するエディット コンティニュのシナリオで使用されます。</span><span class="sxs-lookup"><span data-stu-id="c1583-104">This method is used in edit-and-continue scenarios to update the symbol store to match deltas to the original portable executable (PE) file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1583-105">いずれかのみを指定する必要があります、`filename`または`pIStream`両方のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="c1583-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="c1583-106">場合`filename`を指定すると、シンボル ストアはそのファイル内のシンボルで更新されます。</span><span class="sxs-lookup"><span data-stu-id="c1583-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="c1583-107">場合`pIStream`を指定すると、ストアからのデータで更新されます、<xref:System.Runtime.InteropServices.ComTypes.IStream>します。</span><span class="sxs-lookup"><span data-stu-id="c1583-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1583-108">構文</span><span class="sxs-lookup"><span data-stu-id="c1583-108">Syntax</span></span>  
  
```  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1583-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c1583-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="c1583-110">[in]シンボル ストアを含むファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="c1583-110">[in] The name of the file that contains the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="c1583-111">[in]使用する代わりに、ファイル ストリーム、`filename`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="c1583-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1583-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="c1583-112">Return Value</span></span>  
 <span data-ttu-id="c1583-113">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="c1583-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1583-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="c1583-114">Requirements</span></span>  
 <span data-ttu-id="c1583-115">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c1583-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1583-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1583-116">See also</span></span>

- [<span data-ttu-id="c1583-117">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c1583-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
