---
title: ICLRDebuggingLibraryProvider::ProvideLibrary メソッド
ms.date: 03/30/2017
api_name:
- ICLRDebuggingLibraryProvider.ProvideLibrary Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebuggingLibraryProvider::ProvideLibrary
helpviewer_keywords:
- ProvideLibrary method [.NET Framework debugging]
- ICLRDebuggingLibraryProvider::ProvideLibrary method [.NET Framework debugging]
ms.assetid: 86f06245-9517-49be-8d8c-ca5deaf34c02
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 26dbd7cb5f0dc3a385fe15d6c417d6fb8e1c9bc4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738352"
---
# <a name="iclrdebugginglibraryproviderprovidelibrary-method"></a><span data-ttu-id="fd435-102">ICLRDebuggingLibraryProvider::ProvideLibrary メソッド</span><span class="sxs-lookup"><span data-stu-id="fd435-102">ICLRDebuggingLibraryProvider::ProvideLibrary Method</span></span>
<span data-ttu-id="fd435-103">ライブラリのプロバイダーに共通言語ランタイム (CLR) バージョン固有デバッグ ライブラリを検索しに読み込む要求を許可するコールバック インターフェイスを取得します。</span><span class="sxs-lookup"><span data-stu-id="fd435-103">Gets a library provider callback interface that allows common language runtime (CLR) version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd435-104">構文</span><span class="sxs-lookup"><span data-stu-id="fd435-104">Syntax</span></span>  
  
```cpp  
HRESULT ProvideLibrary(  
     [in] const WCHAR* pwszFileName,  
     [in] DWORD dwTimestamp,  
     [in] DWORD dwSizeOfImage,  
     [out] HMODULE* hModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd435-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fd435-105">Parameters</span></span>  
 `pwszFilename`  
 <span data-ttu-id="fd435-106">[in]要求されているモジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="fd435-106">[in] The name of the module being requested.</span></span>  
  
 `dwTimestamp`  
 <span data-ttu-id="fd435-107">[in]PE ファイルの COFF ファイル ヘッダーに格納されている日付時刻スタンプ。</span><span class="sxs-lookup"><span data-stu-id="fd435-107">[in] The date time stamp stored in the COFF file header of PE files.</span></span>  
  
 `pLibraryProvider`  
 <span data-ttu-id="fd435-108">[in]`SizeOfImage` PE ファイルの COFF 省略可能なファイルのヘッダーに格納されているフィールドです。</span><span class="sxs-lookup"><span data-stu-id="fd435-108">[in] The `SizeOfImage` field stored in the COFF optional file header of PE files.</span></span>  
  
 `hModule`  
 <span data-ttu-id="fd435-109">[out]要求されたモジュールのハンドルです。</span><span class="sxs-lookup"><span data-stu-id="fd435-109">[out] The handle to the requested module.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd435-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="fd435-110">Return Value</span></span>  
 <span data-ttu-id="fd435-111">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="fd435-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="fd435-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fd435-112">HRESULT</span></span>|<span data-ttu-id="fd435-113">説明</span><span class="sxs-lookup"><span data-stu-id="fd435-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fd435-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="fd435-114">S_OK</span></span>|<span data-ttu-id="fd435-115">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="fd435-115">The method completed successfully.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="fd435-116">例外</span><span class="sxs-lookup"><span data-stu-id="fd435-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd435-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="fd435-117">Remarks</span></span>  
 <span data-ttu-id="fd435-118">`ProvideLibrary` mscordbi.dll mscordacwks.dll などの特定の CLR ファイルをデバッグするために必要なモジュールを提供するデバッガーを使用します。</span><span class="sxs-lookup"><span data-stu-id="fd435-118">`ProvideLibrary` allows the debugger to provide modules that are needed for debugging specific CLR files such as mscordbi.dll and mscordacwks.dll.</span></span> <span data-ttu-id="fd435-119">呼び出すまで、有効なままのモジュール ハンドルが、 [iclrdebugging::canunloadnow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md)メソッドは、これら解放される可能性があります、この時点では、ハンドルを解放する呼び出し元の責任のことを示します。</span><span class="sxs-lookup"><span data-stu-id="fd435-119">The module handles have to remain valid until a call to the [ICLRDebugging::CanUnloadNow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) method indicates that they may be freed, at which point it is the caller’s responsibility to free the handles.</span></span>  
  
 <span data-ttu-id="fd435-120">デバッガーは、検索またはデバッグ モジュールを調達、使用可能な手段を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fd435-120">The debugger may use any available means to locate or procure the debugging module.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fd435-121">この機能は、実行可能ファイル、および、場合によって悪意のあるコードが含まれているモジュールを提供する API の呼び出し元を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fd435-121">This feature allows the API caller to provide modules that contain executable, and possibly malicious, code.</span></span> <span data-ttu-id="fd435-122">セキュリティの予防措置として、呼び出し元を使用する必要がありますいない`ProvideLibrary`自体を実行するつもりはないすべてのコードを配布します。</span><span class="sxs-lookup"><span data-stu-id="fd435-122">As a security precaution, the caller should not use `ProvideLibrary` to distribute any code that it is not willing to execute itself.</span></span>  
>   
>  <span data-ttu-id="fd435-123">Mscordbi.dll または mscordacwks.dll などのリリース済みのライブラリで重大なセキュリティ上の問題が検出された場合、shim パッチを適用できるファイルの不適切なバージョンを認識します。</span><span class="sxs-lookup"><span data-stu-id="fd435-123">If a serious security issue is discovered in an already released library, such as mscordbi.dll or mscordacwks.dll, the shim can be patched to recognize the bad versions of the files.</span></span> <span data-ttu-id="fd435-124">Shim のパッチが適用されたバージョンのファイルの要求を発行し、すべての要求に対する応答で提供される場合は、不適切なバージョンを拒否します。</span><span class="sxs-lookup"><span data-stu-id="fd435-124">The shim can then issue requests for the patched versions of the files and reject the bad versions if they are provided in response to any request.</span></span> <span data-ttu-id="fd435-125">これは、ユーザーが、shim の新しいバージョンにパッチを適用する場合にのみに発生します。</span><span class="sxs-lookup"><span data-stu-id="fd435-125">This can occur only if the user has patched to a new version of the shim.</span></span> <span data-ttu-id="fd435-126">未適用のバージョンは、脆弱なままです。</span><span class="sxs-lookup"><span data-stu-id="fd435-126">Unpatched versions will remain vulnerable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd435-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="fd435-127">Requirements</span></span>  
 <span data-ttu-id="fd435-128">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd435-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd435-129">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd435-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd435-130">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd435-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd435-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd435-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd435-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="fd435-132">See also</span></span>

- [<span data-ttu-id="fd435-133">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fd435-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="fd435-134">デバッグ</span><span class="sxs-lookup"><span data-stu-id="fd435-134">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
