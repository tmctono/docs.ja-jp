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
ms.openlocfilehash: 07d2de5d12fd769cb5cce243d9e721bb6fc185a7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615476"
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="7d4c1-102">ISymUnmanagedReader::Initialize メソッド</span><span class="sxs-lookup"><span data-stu-id="7d4c1-102">ISymUnmanagedReader::Initialize Method</span></span>
<span data-ttu-id="7d4c1-103">このリーダーが関連付けられるメタデータインポーターインターフェイスと、モジュールのファイル名を使用して、シンボルリーダーを初期化します。</span><span class="sxs-lookup"><span data-stu-id="7d4c1-103">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7d4c1-104">このメソッドを呼び出すことができるのは1回だけです。他のリーダーメソッドの前に呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d4c1-104">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d4c1-105">構文</span><span class="sxs-lookup"><span data-stu-id="7d4c1-105">Syntax</span></span>  
  
```cpp  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d4c1-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7d4c1-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="7d4c1-107">からこのリーダーが関連付けられるメタデータインポーターインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="7d4c1-107">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="7d4c1-108">からモジュールのファイル名。</span><span class="sxs-lookup"><span data-stu-id="7d4c1-108">[in] The file name of the module.</span></span> <span data-ttu-id="7d4c1-109">代わりに、パラメーターを使用でき `pIStream` ます。</span><span class="sxs-lookup"><span data-stu-id="7d4c1-109">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="7d4c1-110">から検索するパス。</span><span class="sxs-lookup"><span data-stu-id="7d4c1-110">[in] The path to search.</span></span> <span data-ttu-id="7d4c1-111">このパラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="7d4c1-111">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="7d4c1-112">からファイルストリーム。 filename パラメーターの代わりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="7d4c1-112">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d4c1-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="7d4c1-113">Return Value</span></span>  
 <span data-ttu-id="7d4c1-114">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="7d4c1-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d4c1-115">解説</span><span class="sxs-lookup"><span data-stu-id="7d4c1-115">Remarks</span></span>  
 <span data-ttu-id="7d4c1-116">またはパラメーターのいずれか1つだけを指定する必要があります。両方を指定すること `filename` はでき `pIStream` ません。</span><span class="sxs-lookup"><span data-stu-id="7d4c1-116">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="7d4c1-117">`searchPath` パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="7d4c1-117">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d4c1-118">要件</span><span class="sxs-lookup"><span data-stu-id="7d4c1-118">Requirements</span></span>  
 <span data-ttu-id="7d4c1-119">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="7d4c1-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d4c1-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d4c1-120">See also</span></span>

- [<span data-ttu-id="7d4c1-121">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7d4c1-121">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
