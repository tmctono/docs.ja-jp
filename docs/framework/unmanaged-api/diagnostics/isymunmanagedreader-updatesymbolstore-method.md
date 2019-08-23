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
ms.openlocfilehash: d84d4fccb2cb4e500f07f6bfbfb93b8c7b81f5d6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939005"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a><span data-ttu-id="3a129-102">ISymUnmanagedReader::UpdateSymbolStore メソッド</span><span class="sxs-lookup"><span data-stu-id="3a129-102">ISymUnmanagedReader::UpdateSymbolStore Method</span></span>
<span data-ttu-id="3a129-103">既存のシンボル ストアをデルタ シンボル ストアで更新します。</span><span class="sxs-lookup"><span data-stu-id="3a129-103">Updates the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="3a129-104">このメソッドは、元のポータブル実行可能 (PE) ファイルにデルタを一致するようにシンボルストアを更新するために、エディットコンティニュシナリオで使用されます。</span><span class="sxs-lookup"><span data-stu-id="3a129-104">This method is used in edit-and-continue scenarios to update the symbol store to match deltas to the original portable executable (PE) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3a129-105">`filename`またはパラメーターのいずれか1つ`pIStream`だけを指定する必要があります。両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="3a129-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="3a129-106">を`filename`指定した場合、シンボルストアはそのファイル内のシンボルで更新されます。</span><span class="sxs-lookup"><span data-stu-id="3a129-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="3a129-107">を`pIStream`指定した場合、ストアは<xref:System.Runtime.InteropServices.ComTypes.IStream>からのデータで更新されます。</span><span class="sxs-lookup"><span data-stu-id="3a129-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a129-108">構文</span><span class="sxs-lookup"><span data-stu-id="3a129-108">Syntax</span></span>  
  
```cpp  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a129-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3a129-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="3a129-110">からシンボルストアが格納されているファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="3a129-110">[in] The name of the file that contains the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="3a129-111">からパラメーターの`filename`代わりに使用されるファイルストリーム。</span><span class="sxs-lookup"><span data-stu-id="3a129-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a129-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="3a129-112">Return Value</span></span>  
 <span data-ttu-id="3a129-113">メソッドが成功した場合は S_OK を返します。それ以外の場合は E_FAIL またはその他のエラーコードを返します。</span><span class="sxs-lookup"><span data-stu-id="3a129-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a129-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="3a129-114">Requirements</span></span>  
 <span data-ttu-id="3a129-115">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="3a129-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a129-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a129-116">See also</span></span>

- [<span data-ttu-id="3a129-117">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3a129-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
