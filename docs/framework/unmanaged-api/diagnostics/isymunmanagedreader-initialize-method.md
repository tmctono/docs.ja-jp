---
title: ISymUnmanagedReader::Initialize メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::Initialize
helpviewer_keywords:
- ISymUnmanagedReader::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 8f0dd2fe-7df7-464e-91f4-5518c586bb5f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f2dceeb2f0b3aa9f3147157e77087dffbf2d5f85
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939032"
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="45225-102">ISymUnmanagedReader::Initialize メソッド</span><span class="sxs-lookup"><span data-stu-id="45225-102">ISymUnmanagedReader::Initialize Method</span></span>
<span data-ttu-id="45225-103">このリーダーが関連付けられるメタデータインポーターインターフェイスと、モジュールのファイル名を使用して、シンボルリーダーを初期化します。</span><span class="sxs-lookup"><span data-stu-id="45225-103">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="45225-104">このメソッドを呼び出すことができるのは1回だけです。他のリーダーメソッドの前に呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="45225-104">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45225-105">構文</span><span class="sxs-lookup"><span data-stu-id="45225-105">Syntax</span></span>  
  
```cpp  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45225-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="45225-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="45225-107">からこのリーダーが関連付けられるメタデータインポーターインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="45225-107">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="45225-108">からモジュールのファイル名。</span><span class="sxs-lookup"><span data-stu-id="45225-108">[in] The file name of the module.</span></span> <span data-ttu-id="45225-109">代わりに、 `pIStream`パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="45225-109">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="45225-110">から検索するパス。</span><span class="sxs-lookup"><span data-stu-id="45225-110">[in] The path to search.</span></span> <span data-ttu-id="45225-111">このパラメーターは省略できます。</span><span class="sxs-lookup"><span data-stu-id="45225-111">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="45225-112">からファイルストリーム。 filename パラメーターの代わりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="45225-112">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="45225-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="45225-113">Return Value</span></span>  
 <span data-ttu-id="45225-114">メソッドが成功した場合は S_OK を返します。それ以外の場合は E_FAIL またはその他のエラーコードを返します。</span><span class="sxs-lookup"><span data-stu-id="45225-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45225-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="45225-115">Remarks</span></span>  
 <span data-ttu-id="45225-116">または`filename`パラメーターのいずれか1つだけを指定する必要があります。両方を指定することはできません。 `pIStream`</span><span class="sxs-lookup"><span data-stu-id="45225-116">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="45225-117">`searchPath` パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="45225-117">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45225-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="45225-118">Requirements</span></span>  
 <span data-ttu-id="45225-119">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="45225-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45225-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="45225-120">See also</span></span>

- [<span data-ttu-id="45225-121">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="45225-121">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
