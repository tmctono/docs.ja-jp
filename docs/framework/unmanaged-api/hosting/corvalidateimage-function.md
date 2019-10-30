---
title: _CorValidateImage 関数
ms.date: 03/30/2017
api_name:
- _CorValidateImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorValidateImage
helpviewer_keywords:
- _CorValidateImage function [.NET Framework hosting]
ms.assetid: 0117e080-05f9-4772-885d-e1847230947c
topic_type:
- apiref
ms.openlocfilehash: 42da5bb761ba8ce388bd41d46e8fdc4561ad0290
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136881"
---
# <a name="_corvalidateimage-function"></a><span data-ttu-id="48647-102">_CorValidateImage 関数</span><span class="sxs-lookup"><span data-stu-id="48647-102">_CorValidateImage Function</span></span>
<span data-ttu-id="48647-103">マネージド モジュール イメージを検証し、それらが読み込まれると、オペレーティング システム ローダーに通知します。</span><span class="sxs-lookup"><span data-stu-id="48647-103">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48647-104">構文</span><span class="sxs-lookup"><span data-stu-id="48647-104">Syntax</span></span>  
  
```cpp  
STDAPI _CorValidateImage (   
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48647-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="48647-105">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="48647-106">からマネージコードとして検証するイメージの開始位置へのポインター。</span><span class="sxs-lookup"><span data-stu-id="48647-106">[in] A pointer to the starting location of the image to validate as managed code.</span></span> <span data-ttu-id="48647-107">イメージは既にメモリに読み込まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="48647-107">The image must already be loaded into memory.</span></span>  
  
 `FileName`  
 <span data-ttu-id="48647-108">からイメージのファイル名。</span><span class="sxs-lookup"><span data-stu-id="48647-108">[in] The file name of the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48647-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="48647-109">Return Value</span></span>  
 <span data-ttu-id="48647-110">この関数は、`E_INVALIDARG`、`E_OUTOFMEMORY`、`E_UNEXPECTED`、および `E_FAIL`の標準値と、次の値を返します。</span><span class="sxs-lookup"><span data-stu-id="48647-110">This function returns the standard values `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, and `E_FAIL`, as well as the following values.</span></span>  
  
|<span data-ttu-id="48647-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="48647-111">Return value</span></span>|<span data-ttu-id="48647-112">説明</span><span class="sxs-lookup"><span data-stu-id="48647-112">Description</span></span>|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|<span data-ttu-id="48647-113">イメージが無効です。</span><span class="sxs-lookup"><span data-stu-id="48647-113">The image is invalid.</span></span> <span data-ttu-id="48647-114">この値には HRESULT 0xC000007BL があります。</span><span class="sxs-lookup"><span data-stu-id="48647-114">This value has the HRESULT 0xC000007BL.</span></span>|  
|`STATUS_SUCCESS`|<span data-ttu-id="48647-115">イメージは有効です。</span><span class="sxs-lookup"><span data-stu-id="48647-115">The image is valid.</span></span> <span data-ttu-id="48647-116">この値には、HRESULT 0x00000000L が含まれています。</span><span class="sxs-lookup"><span data-stu-id="48647-116">This value has the HRESULT 0x00000000L.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48647-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="48647-117">Remarks</span></span>  
 <span data-ttu-id="48647-118">Windows XP 以降のバージョンでは、オペレーティングシステムローダーは、Common Object File Format (COFF) ヘッダーの COM 記述子ディレクトリビットを調べて、マネージモジュールをチェックします。</span><span class="sxs-lookup"><span data-stu-id="48647-118">In Windows XP and later versions, the operating system loader checks for managed modules by examining the COM Descriptor Directory bit in the common object file format (COFF) header.</span></span> <span data-ttu-id="48647-119">セットビットはマネージモジュールを示します。</span><span class="sxs-lookup"><span data-stu-id="48647-119">A set bit indicates a managed module.</span></span> <span data-ttu-id="48647-120">ローダーがマネージモジュールを検出すると、Mscoree.dll を読み込み、`_CorValidateImage`を呼び出します。これにより、次のアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="48647-120">If the loader detects a managed module, it loads MsCorEE.dll and calls `_CorValidateImage`, which performs the following actions:</span></span>  
  
- <span data-ttu-id="48647-121">イメージが有効なマネージモジュールであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="48647-121">Confirms that the image is a valid managed module.</span></span>  
  
- <span data-ttu-id="48647-122">イメージのエントリポイントを共通言語ランタイム (CLR) のエントリポイントに変更します。</span><span class="sxs-lookup"><span data-stu-id="48647-122">Changes the entry point in the image to an entry point in the common language runtime (CLR).</span></span>  
  
- <span data-ttu-id="48647-123">Windows の64ビットバージョンでは、PE32 から PE32 + 形式に変換することによって、メモリ内のイメージを変更します。</span><span class="sxs-lookup"><span data-stu-id="48647-123">For 64-bit versions of Windows, modifies the image that is in memory by transforming it from PE32 to PE32+ format.</span></span>  
  
- <span data-ttu-id="48647-124">マネージモジュールイメージが読み込まれると、ローダーに戻ります。</span><span class="sxs-lookup"><span data-stu-id="48647-124">Returns to the loader when the managed module images are loaded.</span></span>  
  
 <span data-ttu-id="48647-125">実行可能イメージの場合、オペレーティングシステムローダーは、実行可能ファイルで指定されたエントリポイントに関係なく、 [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="48647-125">For executable images, the operating system loader then calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function, regardless of the entry point specified in the executable.</span></span> <span data-ttu-id="48647-126">DLL アセンブリイメージの場合、ローダーは[Cordllmain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="48647-126">For DLL assembly images, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function.</span></span>  
  
 <span data-ttu-id="48647-127">`_CorExeMain` または `_CorDllMain` は、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="48647-127">`_CorExeMain` or `_CorDllMain` performs the following actions:</span></span>  
  
- <span data-ttu-id="48647-128">CLR を初期化します。</span><span class="sxs-lookup"><span data-stu-id="48647-128">Initializes the CLR.</span></span>  
  
- <span data-ttu-id="48647-129">アセンブリの CLR ヘッダーからマネージエントリポイントを検索します。</span><span class="sxs-lookup"><span data-stu-id="48647-129">Locates the managed entry point from the assembly's CLR header.</span></span>  
  
- <span data-ttu-id="48647-130">実行を開始します。</span><span class="sxs-lookup"><span data-stu-id="48647-130">Begins execution.</span></span>  
  
 <span data-ttu-id="48647-131">ローダーは、マネージモジュールイメージがアンロードされるときに、 [Corimageアンロード](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md)関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="48647-131">The loader calls the [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) function when managed module images are unloaded.</span></span> <span data-ttu-id="48647-132">ただし、この関数は何のアクションも実行しません。これはだけを返します。</span><span class="sxs-lookup"><span data-stu-id="48647-132">However, this function does not perform any action; it just returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48647-133">［要件］</span><span class="sxs-lookup"><span data-stu-id="48647-133">Requirements</span></span>  
 <span data-ttu-id="48647-134">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48647-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48647-135">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="48647-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="48647-136">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="48647-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="48647-137">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48647-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48647-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="48647-138">See also</span></span>

- [<span data-ttu-id="48647-139">メタデータ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="48647-139">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
