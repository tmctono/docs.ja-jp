---
title: GetRequestedRuntimeInfo 関数
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeInfo
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeInfo
helpviewer_keywords:
- GetRequestedRuntimeInfo function [.NET Framework hosting]
ms.assetid: 0dfd7cdc-c116-4e25-b56a-ac7b0378c942
topic_type:
- apiref
ms.openlocfilehash: db721e1ef774c87de0fa7da178463d832a3da756
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178154"
---
# <a name="getrequestedruntimeinfo-function"></a><span data-ttu-id="31f7d-102">GetRequestedRuntimeInfo 関数</span><span class="sxs-lookup"><span data-stu-id="31f7d-102">GetRequestedRuntimeInfo Function</span></span>
<span data-ttu-id="31f7d-103">アプリケーションが要求した共通言語ランタイム (CLR) に関するバージョン情報とディレクトリ情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="31f7d-103">Gets version and directory information about the common language runtime (CLR) requested by an application.</span></span>  
  
 <span data-ttu-id="31f7d-104">この関数は、.NET Framework 4 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="31f7d-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31f7d-105">構文</span><span class="sxs-lookup"><span data-stu-id="31f7d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeInfo (  
    [in]  LPCWSTR  pExe,
    [in]  LPCWSTR  pwszVersion,
    [in]  LPCWSTR  pConfigurationFile,
    [in]  DWORD    startupFlags,
    [in]  DWORD    runtimeInfoFlags,
    [out] LPWSTR   pDirectory,
    [in]  DWORD    dwDirectory,
    [out] DWORD   *dwDirectoryLength,
    [out] LPWSTR   pVersion,
    [in]  DWORD    cchBuffer,
    [out] DWORD   *dwlength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31f7d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="31f7d-106">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="31f7d-107">[in]アプリケーションの名前。</span><span class="sxs-lookup"><span data-stu-id="31f7d-107">[in] The name of the application.</span></span>  
  
 `pwszVersion`  
 <span data-ttu-id="31f7d-108">[in]ランタイムのバージョン番号を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="31f7d-108">[in] A string specifying the version number of the runtime.</span></span>  
  
 `pConfigurationFile`  
 <span data-ttu-id="31f7d-109">[in]に関連付けられている`pExe`構成ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="31f7d-109">[in] The name of the configuration file that is associated with `pExe`.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="31f7d-110">[in][STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)列挙値の 1 つ以上。</span><span class="sxs-lookup"><span data-stu-id="31f7d-110">[in] One or more of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration values.</span></span>  
  
 `runtimeInfoFlags`  
 <span data-ttu-id="31f7d-111">[in]1 つ以上の[RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md)列挙値。</span><span class="sxs-lookup"><span data-stu-id="31f7d-111">[in] One or more of the [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) enumeration values.</span></span>  
  
 `pDirectory`  
 <span data-ttu-id="31f7d-112">[アウト]正常終了したランタイムへのディレクトリ パスを格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="31f7d-112">[out] A buffer that contains the directory path to the runtime upon successful completion.</span></span>  
  
 `dwDirectory`  
 <span data-ttu-id="31f7d-113">[in]ディレクトリ バッファの長さ。</span><span class="sxs-lookup"><span data-stu-id="31f7d-113">[in] The length of the directory buffer.</span></span>  
  
 `dwDirectoryLength`  
 <span data-ttu-id="31f7d-114">[アウト]ディレクトリ パス文字列の長さへのポインター。</span><span class="sxs-lookup"><span data-stu-id="31f7d-114">[out] A pointer to the length of the directory path string.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="31f7d-115">[アウト]正常終了したランタイムのバージョン番号を格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="31f7d-115">[out] A buffer that contains the version number of the runtime upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="31f7d-116">[in]バージョン文字列バッファーの長さ。</span><span class="sxs-lookup"><span data-stu-id="31f7d-116">[in] The length of the version string buffer.</span></span>  
  
 `dwlength`  
 <span data-ttu-id="31f7d-117">[アウト]バージョン文字列の長さへのポインター。</span><span class="sxs-lookup"><span data-stu-id="31f7d-117">[out] A pointer to the length of the version string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="31f7d-118">戻り値</span><span class="sxs-lookup"><span data-stu-id="31f7d-118">Return Value</span></span>  
 <span data-ttu-id="31f7d-119">このメソッドは、WinError.h で定義されている次の値に加えて、標準のコンポーネント オブジェクト モデル (COM) エラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="31f7d-119">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="31f7d-120">リターン コード</span><span class="sxs-lookup"><span data-stu-id="31f7d-120">Return code</span></span>|<span data-ttu-id="31f7d-121">説明</span><span class="sxs-lookup"><span data-stu-id="31f7d-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="31f7d-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="31f7d-122">S_OK</span></span>|<span data-ttu-id="31f7d-123">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="31f7d-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="31f7d-124">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="31f7d-124">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="31f7d-125">ディレクトリ バッファのサイズが、ディレクトリ パスを格納するのに十分ではありません。</span><span class="sxs-lookup"><span data-stu-id="31f7d-125">The directory buffer is not large enough to store the directory path.</span></span><br /><br /> <span data-ttu-id="31f7d-126">- または -</span><span class="sxs-lookup"><span data-stu-id="31f7d-126">- or -</span></span><br /><br /> <span data-ttu-id="31f7d-127">バージョン バッファーのサイズが、バージョン文字列を格納するのに十分ではありません。</span><span class="sxs-lookup"><span data-stu-id="31f7d-127">The version buffer is not large enough to store the version string.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31f7d-128">解説</span><span class="sxs-lookup"><span data-stu-id="31f7d-128">Remarks</span></span>  
 <span data-ttu-id="31f7d-129">この`GetRequestedRuntimeInfo`メソッドは、プロセスに読み込まれたバージョンに関する実行時情報を返します。</span><span class="sxs-lookup"><span data-stu-id="31f7d-129">The `GetRequestedRuntimeInfo` method returns run-time information about the version loaded into the process, which is not necessarily the latest version installed on the computer.</span></span>  
  
 <span data-ttu-id="31f7d-130">.NET Framework Version 2.0 では、次の方法を使用して、インストールされている`GetRequestedRuntimeInfo`最新バージョンに関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="31f7d-130">In the .NET Framework version 2.0, you can get information about the latest installed version by using the `GetRequestedRuntimeInfo` method as follows:</span></span>  
  
- <span data-ttu-id="31f7d-131">`pExe`、 、`pwszVersion`および`pConfigurationFile`パラメーターを null として指定します。</span><span class="sxs-lookup"><span data-stu-id="31f7d-131">Specify the `pExe`, `pwszVersion`, and `pConfigurationFile` parameters as null.</span></span>  
  
- <span data-ttu-id="31f7d-132">パラメーターの`RUNTIME_INFO_FLAGS`列挙体にRUNTIME_INFO_UPGRADE_VERSIONフラグを`runtimeInfoFlags`指定します。</span><span class="sxs-lookup"><span data-stu-id="31f7d-132">Specify the RUNTIME_INFO_UPGRADE_VERSION flag in the `RUNTIME_INFO_FLAGS` enumerations for the `runtimeInfoFlags` parameter.</span></span>  
  
 <span data-ttu-id="31f7d-133">この`GetRequestedRuntimeInfo`メソッドは、次の状況では最新の CLR バージョンを返しません。</span><span class="sxs-lookup"><span data-stu-id="31f7d-133">The `GetRequestedRuntimeInfo` method does not return the latest CLR version in the following circumstances:</span></span>  
  
- <span data-ttu-id="31f7d-134">特定の CLR バージョンの読み込みを指定するアプリケーション構成ファイルが存在します。</span><span class="sxs-lookup"><span data-stu-id="31f7d-134">An application configuration file that specifies loading a particular CLR version exists.</span></span> <span data-ttu-id="31f7d-135">パラメータに null を指定した場合でも、.NET Framework では構成`pConfigurationFile`ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="31f7d-135">Note that the .NET Framework will use the configuration file even if you specify null for the `pConfigurationFile` parameter.</span></span>  
  
- <span data-ttu-id="31f7d-136">メソッド[は](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)、以前の CLR バージョンを指定して呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="31f7d-136">The [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) method was called specifying an earlier CLR version.</span></span>  
  
- <span data-ttu-id="31f7d-137">以前の CLR バージョン用にコンパイルされたアプリケーションが現在実行されています。</span><span class="sxs-lookup"><span data-stu-id="31f7d-137">An application that was compiled for an earlier CLR version is currently running.</span></span>  
  
 <span data-ttu-id="31f7d-138">パラメーターには`runtimeInfoFlags`、`RUNTIME_INFO_FLAGS`一度に列挙のアーキテクチャ定数の 1 つだけを指定できます。</span><span class="sxs-lookup"><span data-stu-id="31f7d-138">For the `runtimeInfoFlags` parameter, you can specify only one of the architecture constants of the `RUNTIME_INFO_FLAGS` enumeration at a time:</span></span>  
  
- <span data-ttu-id="31f7d-139">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="31f7d-139">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
- <span data-ttu-id="31f7d-140">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="31f7d-140">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
- <span data-ttu-id="31f7d-141">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="31f7d-141">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31f7d-142">必要条件</span><span class="sxs-lookup"><span data-stu-id="31f7d-142">Requirements</span></span>  
 <span data-ttu-id="31f7d-143">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31f7d-143">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31f7d-144">**ヘッダー:** msCorEE.h</span><span class="sxs-lookup"><span data-stu-id="31f7d-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="31f7d-145">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="31f7d-145">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="31f7d-146">**.NET Framework のバージョン:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31f7d-146">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31f7d-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="31f7d-147">See also</span></span>

- [<span data-ttu-id="31f7d-148">GetRequestedRuntimeVersion 関数</span><span class="sxs-lookup"><span data-stu-id="31f7d-148">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="31f7d-149">GetVersionFromProcess 関数</span><span class="sxs-lookup"><span data-stu-id="31f7d-149">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="31f7d-150">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="31f7d-150">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
