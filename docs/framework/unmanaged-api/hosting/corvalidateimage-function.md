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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6f1d76ef5cf36bcbab29a33647520663f822798
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770030"
---
# <a name="corvalidateimage-function"></a><span data-ttu-id="aed18-102">_CorValidateImage 関数</span><span class="sxs-lookup"><span data-stu-id="aed18-102">_CorValidateImage Function</span></span>
<span data-ttu-id="aed18-103">マネージド モジュール イメージを検証し、それらが読み込まれると、オペレーティング システム ローダーに通知します。</span><span class="sxs-lookup"><span data-stu-id="aed18-103">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aed18-104">構文</span><span class="sxs-lookup"><span data-stu-id="aed18-104">Syntax</span></span>  
  
```cpp  
STDAPI _CorValidateImage (   
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aed18-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aed18-105">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="aed18-106">[in]イメージを検証する際の開始位置へのポインターはマネージ コードです。</span><span class="sxs-lookup"><span data-stu-id="aed18-106">[in] A pointer to the starting location of the image to validate as managed code.</span></span> <span data-ttu-id="aed18-107">イメージは、メモリに既に読み込まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="aed18-107">The image must already be loaded into memory.</span></span>  
  
 `FileName`  
 <span data-ttu-id="aed18-108">[in]イメージのファイル名。</span><span class="sxs-lookup"><span data-stu-id="aed18-108">[in] The file name of the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aed18-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="aed18-109">Return Value</span></span>  
 <span data-ttu-id="aed18-110">この関数は、標準の値を返します`E_INVALIDARG`、 `E_OUTOFMEMORY`、 `E_UNEXPECTED`、および`E_FAIL`、次の値。</span><span class="sxs-lookup"><span data-stu-id="aed18-110">This function returns the standard values `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, and `E_FAIL`, as well as the following values.</span></span>  
  
|<span data-ttu-id="aed18-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="aed18-111">Return value</span></span>|<span data-ttu-id="aed18-112">説明</span><span class="sxs-lookup"><span data-stu-id="aed18-112">Description</span></span>|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|<span data-ttu-id="aed18-113">イメージが無効です。</span><span class="sxs-lookup"><span data-stu-id="aed18-113">The image is invalid.</span></span> <span data-ttu-id="aed18-114">この値は、HRESULT 0xC000007BL を持っています。</span><span class="sxs-lookup"><span data-stu-id="aed18-114">This value has the HRESULT 0xC000007BL.</span></span>|  
|`STATUS_SUCCESS`|<span data-ttu-id="aed18-115">イメージが無効です。</span><span class="sxs-lookup"><span data-stu-id="aed18-115">The image is valid.</span></span> <span data-ttu-id="aed18-116">この値は、HRESULT 0x00000000L を持っています。</span><span class="sxs-lookup"><span data-stu-id="aed18-116">This value has the HRESULT 0x00000000L.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aed18-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="aed18-117">Remarks</span></span>  
 <span data-ttu-id="aed18-118">Windows XP およびそれ以降のバージョンでは、オペレーティング システム ローダーがマネージ モジュールの一般的なオブジェクト ファイルの形式 (COFF) ヘッダーで COM 記述子ディレクトリ ビットを調べることでチェックします。</span><span class="sxs-lookup"><span data-stu-id="aed18-118">In Windows XP and later versions, the operating system loader checks for managed modules by examining the COM Descriptor Directory bit in the common object file format (COFF) header.</span></span> <span data-ttu-id="aed18-119">設定済みビットでは、マネージ モジュールを示します。</span><span class="sxs-lookup"><span data-stu-id="aed18-119">A set bit indicates a managed module.</span></span> <span data-ttu-id="aed18-120">MsCorEE.dll と呼び出しを読み込む場合は、ローダーは、マネージ モジュールを検出、 `_CorValidateImage`、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="aed18-120">If the loader detects a managed module, it loads MsCorEE.dll and calls `_CorValidateImage`, which performs the following actions:</span></span>  
  
- <span data-ttu-id="aed18-121">有効なマネージ モジュール イメージがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="aed18-121">Confirms that the image is a valid managed module.</span></span>  
  
- <span data-ttu-id="aed18-122">共通言語ランタイム (CLR) のエントリ ポイントにイメージ内のエントリ ポイントを変更します。</span><span class="sxs-lookup"><span data-stu-id="aed18-122">Changes the entry point in the image to an entry point in the common language runtime (CLR).</span></span>  
  
- <span data-ttu-id="aed18-123">Windows の 64 ビット バージョンでは、PE32 から pe 32 + 形式に変換することによってメモリにある画像を変更します。</span><span class="sxs-lookup"><span data-stu-id="aed18-123">For 64-bit versions of Windows, modifies the image that is in memory by transforming it from PE32 to PE32+ format.</span></span>  
  
- <span data-ttu-id="aed18-124">マネージ モジュール イメージが読み込まれるときにローダーに戻ります。</span><span class="sxs-lookup"><span data-stu-id="aed18-124">Returns to the loader when the managed module images are loaded.</span></span>  
  
 <span data-ttu-id="aed18-125">実行可能イメージでは、オペレーティング システム ローダーを呼び出して、 [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)関数の実行可能ファイルで指定されたエントリ ポイントに関係なく、します。</span><span class="sxs-lookup"><span data-stu-id="aed18-125">For executable images, the operating system loader then calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function, regardless of the entry point specified in the executable.</span></span> <span data-ttu-id="aed18-126">ローダーの呼び出し、DLL アセンブリのイメージ、 [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)関数。</span><span class="sxs-lookup"><span data-stu-id="aed18-126">For DLL assembly images, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function.</span></span>  
  
 <span data-ttu-id="aed18-127">`_CorExeMain` または`_CorDllMain`は、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="aed18-127">`_CorExeMain` or `_CorDllMain` performs the following actions:</span></span>  
  
- <span data-ttu-id="aed18-128">CLR を初期化します。</span><span class="sxs-lookup"><span data-stu-id="aed18-128">Initializes the CLR.</span></span>  
  
- <span data-ttu-id="aed18-129">アセンブリの CLR ヘッダーからマネージ エントリ ポイントを検索します。</span><span class="sxs-lookup"><span data-stu-id="aed18-129">Locates the managed entry point from the assembly's CLR header.</span></span>  
  
- <span data-ttu-id="aed18-130">実行を開始します。</span><span class="sxs-lookup"><span data-stu-id="aed18-130">Begins execution.</span></span>  
  
 <span data-ttu-id="aed18-131">ローダーの呼び出し、 [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md)を管理するときに関数モジュール イメージは読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="aed18-131">The loader calls the [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) function when managed module images are unloaded.</span></span> <span data-ttu-id="aed18-132">ただし、この関数が任意のアクションを実行しません返すだけです。</span><span class="sxs-lookup"><span data-stu-id="aed18-132">However, this function does not perform any action; it just returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aed18-133">必要条件</span><span class="sxs-lookup"><span data-stu-id="aed18-133">Requirements</span></span>  
 <span data-ttu-id="aed18-134">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aed18-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aed18-135">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="aed18-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aed18-136">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="aed18-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="aed18-137">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aed18-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aed18-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="aed18-138">See also</span></span>

- [<span data-ttu-id="aed18-139">メタデータ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="aed18-139">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
