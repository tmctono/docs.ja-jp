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
ms.openlocfilehash: cd1d9e768698115bee22e35699b044e0c3526d2d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136319"
---
# <a name="getrequestedruntimeinfo-function"></a><span data-ttu-id="9688e-102">GetRequestedRuntimeInfo 関数</span><span class="sxs-lookup"><span data-stu-id="9688e-102">GetRequestedRuntimeInfo Function</span></span>
<span data-ttu-id="9688e-103">アプリケーションによって要求された共通言語ランタイム (CLR) に関するバージョンとディレクトリ情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="9688e-103">Gets version and directory information about the common language runtime (CLR) requested by an application.</span></span>  
  
 <span data-ttu-id="9688e-104">この関数は .NET Framework 4 で非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="9688e-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9688e-105">構文</span><span class="sxs-lookup"><span data-stu-id="9688e-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="9688e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9688e-106">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="9688e-107">からアプリケーションの名前。</span><span class="sxs-lookup"><span data-stu-id="9688e-107">[in] The name of the application.</span></span>  
  
 `pwszVersion`  
 <span data-ttu-id="9688e-108">からランタイムのバージョン番号を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="9688e-108">[in] A string specifying the version number of the runtime.</span></span>  
  
 `pConfigurationFile`  
 <span data-ttu-id="9688e-109">から`pExe`に関連付けられている構成ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="9688e-109">[in] The name of the configuration file that is associated with `pExe`.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="9688e-110">から1つまたは複数の[STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)列挙値。</span><span class="sxs-lookup"><span data-stu-id="9688e-110">[in] One or more of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration values.</span></span>  
  
 `runtimeInfoFlags`  
 <span data-ttu-id="9688e-111">から1つまたは複数の[RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md)列挙値。</span><span class="sxs-lookup"><span data-stu-id="9688e-111">[in] One or more of the [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) enumeration values.</span></span>  
  
 `pDirectory`  
 <span data-ttu-id="9688e-112">入出力正常に完了したときのランタイムへのディレクトリパスを格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="9688e-112">[out] A buffer that contains the directory path to the runtime upon successful completion.</span></span>  
  
 `dwDirectory`  
 <span data-ttu-id="9688e-113">からディレクトリバッファーの長さ。</span><span class="sxs-lookup"><span data-stu-id="9688e-113">[in] The length of the directory buffer.</span></span>  
  
 `dwDirectoryLength`  
 <span data-ttu-id="9688e-114">入出力ディレクトリパス文字列の長さへのポインター。</span><span class="sxs-lookup"><span data-stu-id="9688e-114">[out] A pointer to the length of the directory path string.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="9688e-115">入出力正常に完了したときのランタイムのバージョン番号を格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="9688e-115">[out] A buffer that contains the version number of the runtime upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="9688e-116">からバージョン文字列バッファーの長さ。</span><span class="sxs-lookup"><span data-stu-id="9688e-116">[in] The length of the version string buffer.</span></span>  
  
 `dwlength`  
 <span data-ttu-id="9688e-117">入出力バージョン文字列の長さへのポインター。</span><span class="sxs-lookup"><span data-stu-id="9688e-117">[out] A pointer to the length of the version string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9688e-118">戻り値</span><span class="sxs-lookup"><span data-stu-id="9688e-118">Return Value</span></span>  
 <span data-ttu-id="9688e-119">このメソッドは、次の値に加えて、Winerror.h で定義されている標準のコンポーネントオブジェクトモデル (COM) エラーコードを返します。</span><span class="sxs-lookup"><span data-stu-id="9688e-119">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="9688e-120">リターン コード</span><span class="sxs-lookup"><span data-stu-id="9688e-120">Return code</span></span>|<span data-ttu-id="9688e-121">説明</span><span class="sxs-lookup"><span data-stu-id="9688e-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="9688e-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="9688e-122">S_OK</span></span>|<span data-ttu-id="9688e-123">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="9688e-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="9688e-124">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="9688e-124">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="9688e-125">ディレクトリのバッファーが、ディレクトリパスを格納するのに十分な大きさではありません。</span><span class="sxs-lookup"><span data-stu-id="9688e-125">The directory buffer is not large enough to store the directory path.</span></span><br /><br /> <span data-ttu-id="9688e-126">または</span><span class="sxs-lookup"><span data-stu-id="9688e-126">- or -</span></span><br /><br /> <span data-ttu-id="9688e-127">バージョンバッファーが、バージョン文字列を格納するのに十分な大きさではありません。</span><span class="sxs-lookup"><span data-stu-id="9688e-127">The version buffer is not large enough to store the version string.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9688e-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="9688e-128">Remarks</span></span>  
 <span data-ttu-id="9688e-129">`GetRequestedRuntimeInfo` メソッドは、プロセスに読み込まれたバージョンに関する実行時の情報を返します。これは、必ずしもコンピューターにインストールされている最新バージョンではありません。</span><span class="sxs-lookup"><span data-stu-id="9688e-129">The `GetRequestedRuntimeInfo` method returns run-time information about the version loaded into the process, which is not necessarily the latest version installed on the computer.</span></span>  
  
 <span data-ttu-id="9688e-130">.NET Framework バージョン2.0 では、次のように `GetRequestedRuntimeInfo` 方法を使用して、インストールされている最新のバージョンに関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="9688e-130">In the .NET Framework version 2.0, you can get information about the latest installed version by using the `GetRequestedRuntimeInfo` method as follows:</span></span>  
  
- <span data-ttu-id="9688e-131">`pExe`、`pwszVersion`、および `pConfigurationFile` パラメーターを null として指定します。</span><span class="sxs-lookup"><span data-stu-id="9688e-131">Specify the `pExe`, `pwszVersion`, and `pConfigurationFile` parameters as null.</span></span>  
  
- <span data-ttu-id="9688e-132">`runtimeInfoFlags` パラメーターの `RUNTIME_INFO_FLAGS` 列挙で、RUNTIME_INFO_UPGRADE_VERSION フラグを指定します。</span><span class="sxs-lookup"><span data-stu-id="9688e-132">Specify the RUNTIME_INFO_UPGRADE_VERSION flag in the `RUNTIME_INFO_FLAGS` enumerations for the `runtimeInfoFlags` parameter.</span></span>  
  
 <span data-ttu-id="9688e-133">`GetRequestedRuntimeInfo` メソッドは、次のような状況では、最新の CLR バージョンを返しません。</span><span class="sxs-lookup"><span data-stu-id="9688e-133">The `GetRequestedRuntimeInfo` method does not return the latest CLR version in the following circumstances:</span></span>  
  
- <span data-ttu-id="9688e-134">特定の CLR バージョンの読み込みを指定するアプリケーション構成ファイルが存在します。</span><span class="sxs-lookup"><span data-stu-id="9688e-134">An application configuration file that specifies loading a particular CLR version exists.</span></span> <span data-ttu-id="9688e-135">`pConfigurationFile` パラメーターに null を指定した場合でも、.NET Framework は構成ファイルを使用することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9688e-135">Note that the .NET Framework will use the configuration file even if you specify null for the `pConfigurationFile` parameter.</span></span>  
  
- <span data-ttu-id="9688e-136">[Corbindtoruntimeex](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)メソッドが、以前の CLR バージョンを指定して呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="9688e-136">The [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) method was called specifying an earlier CLR version.</span></span>  
  
- <span data-ttu-id="9688e-137">以前のバージョンの CLR 用にコンパイルされたアプリケーションが現在実行されています。</span><span class="sxs-lookup"><span data-stu-id="9688e-137">An application that was compiled for an earlier CLR version is currently running.</span></span>  
  
 <span data-ttu-id="9688e-138">`runtimeInfoFlags` パラメーターでは、`RUNTIME_INFO_FLAGS` 列挙体のアーキテクチャ定数を一度に1つだけ指定できます。</span><span class="sxs-lookup"><span data-stu-id="9688e-138">For the `runtimeInfoFlags` parameter, you can specify only one of the architecture constants of the `RUNTIME_INFO_FLAGS` enumeration at a time:</span></span>  
  
- <span data-ttu-id="9688e-139">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="9688e-139">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
- <span data-ttu-id="9688e-140">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="9688e-140">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
- <span data-ttu-id="9688e-141">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="9688e-141">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9688e-142">［要件］</span><span class="sxs-lookup"><span data-stu-id="9688e-142">Requirements</span></span>  
 <span data-ttu-id="9688e-143">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9688e-143">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9688e-144">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9688e-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9688e-145">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9688e-145">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9688e-146">**.NET Framework のバージョン:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9688e-146">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9688e-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="9688e-147">See also</span></span>

- [<span data-ttu-id="9688e-148">GetRequestedRuntimeVersion 関数</span><span class="sxs-lookup"><span data-stu-id="9688e-148">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="9688e-149">GetVersionFromProcess 関数</span><span class="sxs-lookup"><span data-stu-id="9688e-149">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="9688e-150">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="9688e-150">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
