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
ms.openlocfilehash: 3a6da0e845fa50d090cdf0808b211a5806c40961
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178213"
---
# <a name="_corvalidateimage-function"></a><span data-ttu-id="38d98-102">_CorValidateImage 関数</span><span class="sxs-lookup"><span data-stu-id="38d98-102">_CorValidateImage Function</span></span>
<span data-ttu-id="38d98-103">マネージド モジュール イメージを検証し、それらが読み込まれると、オペレーティング システム ローダーに通知します。</span><span class="sxs-lookup"><span data-stu-id="38d98-103">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38d98-104">構文</span><span class="sxs-lookup"><span data-stu-id="38d98-104">Syntax</span></span>  
  
```cpp  
STDAPI _CorValidateImage (
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38d98-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="38d98-105">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="38d98-106">[in]マネージ コードとして検証するイメージの開始位置へのポインター。</span><span class="sxs-lookup"><span data-stu-id="38d98-106">[in] A pointer to the starting location of the image to validate as managed code.</span></span> <span data-ttu-id="38d98-107">イメージはメモリに読み込まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="38d98-107">The image must already be loaded into memory.</span></span>  
  
 `FileName`  
 <span data-ttu-id="38d98-108">[in]イメージのファイル名。</span><span class="sxs-lookup"><span data-stu-id="38d98-108">[in] The file name of the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="38d98-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="38d98-109">Return Value</span></span>  
 <span data-ttu-id="38d98-110">この関数は、標準値`E_INVALIDARG` `E_OUTOFMEMORY`、 `E_UNEXPECTED`、 `E_FAIL`、および 、 、および 、 を返します。</span><span class="sxs-lookup"><span data-stu-id="38d98-110">This function returns the standard values `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, and `E_FAIL`, as well as the following values.</span></span>  
  
|<span data-ttu-id="38d98-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="38d98-111">Return value</span></span>|<span data-ttu-id="38d98-112">説明</span><span class="sxs-lookup"><span data-stu-id="38d98-112">Description</span></span>|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|<span data-ttu-id="38d98-113">イメージが無効です。</span><span class="sxs-lookup"><span data-stu-id="38d98-113">The image is invalid.</span></span> <span data-ttu-id="38d98-114">この値は、HRESULT 0xC000007BL を持ちます。</span><span class="sxs-lookup"><span data-stu-id="38d98-114">This value has the HRESULT 0xC000007BL.</span></span>|  
|`STATUS_SUCCESS`|<span data-ttu-id="38d98-115">イメージは有効です。</span><span class="sxs-lookup"><span data-stu-id="38d98-115">The image is valid.</span></span> <span data-ttu-id="38d98-116">この値は、HRESULT 0x0000000L を持ちます。</span><span class="sxs-lookup"><span data-stu-id="38d98-116">This value has the HRESULT 0x00000000L.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38d98-117">解説</span><span class="sxs-lookup"><span data-stu-id="38d98-117">Remarks</span></span>  
 <span data-ttu-id="38d98-118">Windows XP 以降のバージョンでは、オペレーティング システム ローダーは、共通オブジェクト ファイル形式 (COFF) ヘッダーの COM 記述子ディレクトリ ビットを調べることによって、マネージ モジュールをチェックします。</span><span class="sxs-lookup"><span data-stu-id="38d98-118">In Windows XP and later versions, the operating system loader checks for managed modules by examining the COM Descriptor Directory bit in the common object file format (COFF) header.</span></span> <span data-ttu-id="38d98-119">セット ビットは、マネージ モジュールを示します。</span><span class="sxs-lookup"><span data-stu-id="38d98-119">A set bit indicates a managed module.</span></span> <span data-ttu-id="38d98-120">ローダーがマネージ モジュールを検出すると、MsCorEE.dll`_CorValidateImage`が読み込まれ、次のアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="38d98-120">If the loader detects a managed module, it loads MsCorEE.dll and calls `_CorValidateImage`, which performs the following actions:</span></span>  
  
- <span data-ttu-id="38d98-121">イメージが有効なマネージ モジュールであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="38d98-121">Confirms that the image is a valid managed module.</span></span>  
  
- <span data-ttu-id="38d98-122">イメージ内のエントリ ポイントを共通言語ランタイム (CLR) のエントリ ポイントに変更します。</span><span class="sxs-lookup"><span data-stu-id="38d98-122">Changes the entry point in the image to an entry point in the common language runtime (CLR).</span></span>  
  
- <span data-ttu-id="38d98-123">64 ビット バージョンの Windows では、メモリ内のイメージを PE32 から PE32+ 形式に変換して変更します。</span><span class="sxs-lookup"><span data-stu-id="38d98-123">For 64-bit versions of Windows, modifies the image that is in memory by transforming it from PE32 to PE32+ format.</span></span>  
  
- <span data-ttu-id="38d98-124">マネージ モジュール イメージが読み込まれたときにローダーに戻ります。</span><span class="sxs-lookup"><span data-stu-id="38d98-124">Returns to the loader when the managed module images are loaded.</span></span>  
  
 <span data-ttu-id="38d98-125">実行可能イメージの場合、オペレーティング システム ローダーは、実行可能ファイルで指定されたエントリ ポイントに関係なく[、_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="38d98-125">For executable images, the operating system loader then calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function, regardless of the entry point specified in the executable.</span></span> <span data-ttu-id="38d98-126">DLL アセンブリ イメージの場合、ローダーは[_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="38d98-126">For DLL assembly images, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function.</span></span>  
  
 <span data-ttu-id="38d98-127">`_CorExeMain`または`_CorDllMain`、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="38d98-127">`_CorExeMain` or `_CorDllMain` performs the following actions:</span></span>  
  
- <span data-ttu-id="38d98-128">CLR を初期化します。</span><span class="sxs-lookup"><span data-stu-id="38d98-128">Initializes the CLR.</span></span>  
  
- <span data-ttu-id="38d98-129">アセンブリの CLR ヘッダーからマネージ エントリ ポイントを検索します。</span><span class="sxs-lookup"><span data-stu-id="38d98-129">Locates the managed entry point from the assembly's CLR header.</span></span>  
  
- <span data-ttu-id="38d98-130">実行を開始します。</span><span class="sxs-lookup"><span data-stu-id="38d98-130">Begins execution.</span></span>  
  
 <span data-ttu-id="38d98-131">ローダーは、マネージ モジュール イメージがアンロードされるときに[_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md)関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="38d98-131">The loader calls the [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) function when managed module images are unloaded.</span></span> <span data-ttu-id="38d98-132">ただし、この関数はアクションを実行しません。それはちょうど戻ります。</span><span class="sxs-lookup"><span data-stu-id="38d98-132">However, this function does not perform any action; it just returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38d98-133">必要条件</span><span class="sxs-lookup"><span data-stu-id="38d98-133">Requirements</span></span>  
 <span data-ttu-id="38d98-134">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38d98-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38d98-135">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="38d98-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="38d98-136">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="38d98-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="38d98-137">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38d98-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38d98-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="38d98-138">See also</span></span>

- [<span data-ttu-id="38d98-139">メタデータ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="38d98-139">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
