---
title: GetVersionFromProcess 関数
ms.date: 03/30/2017
api_name:
- GetVersionFromProcess
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetVersionFromProcess
helpviewer_keywords:
- GetVersionFromProcess function [.NET Framework hosting]
ms.assetid: a9f7f824-64a1-408d-8607-91c7f19d21fe
topic_type:
- apiref
ms.openlocfilehash: 76c033b11f3212241827d74f4fe18ee881f20b64
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127033"
---
# <a name="getversionfromprocess-function"></a><span data-ttu-id="f60d7-102">GetVersionFromProcess 関数</span><span class="sxs-lookup"><span data-stu-id="f60d7-102">GetVersionFromProcess Function</span></span>
<span data-ttu-id="f60d7-103">指定したプロセスハンドルに関連付けられている共通言語ランタイム (CLR) のバージョン番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="f60d7-103">Gets the version number of the common language runtime (CLR) that is associated with the specified process handle.</span></span>  
  
 <span data-ttu-id="f60d7-104">この関数は .NET Framework 4 で非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="f60d7-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f60d7-105">構文</span><span class="sxs-lookup"><span data-stu-id="f60d7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f60d7-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f60d7-106">Parameters</span></span>  
 `hProcess`  
 <span data-ttu-id="f60d7-107">からプロセスを処理するハンドル。</span><span class="sxs-lookup"><span data-stu-id="f60d7-107">[in] A handle to a process.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="f60d7-108">入出力メソッドが正常に完了したときのバージョン番号の文字列を格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="f60d7-108">[out] A buffer that contains the version number string upon successful completion of the method.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="f60d7-109">からバージョンバッファーの長さ。</span><span class="sxs-lookup"><span data-stu-id="f60d7-109">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="f60d7-110">入出力バージョン番号文字列の長さへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f60d7-110">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f60d7-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="f60d7-111">Return Value</span></span>  
 <span data-ttu-id="f60d7-112">このメソッドは、次の値に加えて、Winerror.h で定義されている標準のコンポーネントオブジェクトモデル (COM) エラーコードを返します。</span><span class="sxs-lookup"><span data-stu-id="f60d7-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="f60d7-113">リターン コード</span><span class="sxs-lookup"><span data-stu-id="f60d7-113">Return code</span></span>|<span data-ttu-id="f60d7-114">説明</span><span class="sxs-lookup"><span data-stu-id="f60d7-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="f60d7-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="f60d7-115">S_OK</span></span>|<span data-ttu-id="f60d7-116">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="f60d7-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="f60d7-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f60d7-117">E_INVALIDARG</span></span>|<span data-ttu-id="f60d7-118">`pVersion` が null で `cchBuffer` が null ではないか、またはその逆です。</span><span class="sxs-lookup"><span data-stu-id="f60d7-118">`pVersion` is null and `cchBuffer` is not null, or vice versa.</span></span><br /><br /> <span data-ttu-id="f60d7-119">-または-</span><span class="sxs-lookup"><span data-stu-id="f60d7-119">-or-</span></span><br /><br /> <span data-ttu-id="f60d7-120">`hProcess` がプロセスに対して有効なハンドルではありません。</span><span class="sxs-lookup"><span data-stu-id="f60d7-120">`hProcess` is not a valid handle to a process.</span></span><br /><br /> <span data-ttu-id="f60d7-121">-または-</span><span class="sxs-lookup"><span data-stu-id="f60d7-121">-or-</span></span><br /><br /> <span data-ttu-id="f60d7-122">CLR が読み込まれていません。</span><span class="sxs-lookup"><span data-stu-id="f60d7-122">The CLR is not loaded.</span></span>|  
|<span data-ttu-id="f60d7-123">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="f60d7-123">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="f60d7-124">`cchBuffer` が null であるか、またはバージョン文字列の長さを下回っています。</span><span class="sxs-lookup"><span data-stu-id="f60d7-124">`cchBuffer` is null or less than the length of the version string.</span></span>|  
|<span data-ttu-id="f60d7-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="f60d7-125">E_NOTIMPL</span></span>|<span data-ttu-id="f60d7-126">この方法は、Microsoft Windows 95、Microsoft Windows 98、または Microsoft Windows Millennium Edition オペレーティングシステムでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="f60d7-126">This method is not available on the Microsoft Windows 95, Microsoft Windows 98, or Microsoft Windows Millennium Edition operating system.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f60d7-127">［要件］</span><span class="sxs-lookup"><span data-stu-id="f60d7-127">Requirements</span></span>  
 <span data-ttu-id="f60d7-128">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f60d7-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f60d7-129">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f60d7-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f60d7-130">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f60d7-130">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f60d7-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f60d7-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f60d7-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="f60d7-132">See also</span></span>

- [<span data-ttu-id="f60d7-133">GetRequestedRuntimeInfo 関数</span><span class="sxs-lookup"><span data-stu-id="f60d7-133">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="f60d7-134">GetRequestedRuntimeVersion 関数</span><span class="sxs-lookup"><span data-stu-id="f60d7-134">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="f60d7-135">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="f60d7-135">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
