---
title: LoadLibraryShim 関数
ms.date: 03/30/2017
api_name:
- LoadLibraryShim
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LoadLibraryShim
helpviewer_keywords:
- LoadLibraryShim function [.NET Framework hosting]
ms.assetid: 30931874-4d0e-4df1-b3d1-e425b50655d1
topic_type:
- apiref
ms.openlocfilehash: 1759ee2ecf08322b745a4f80a62b24596c4504cb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123251"
---
# <a name="loadlibraryshim-function"></a><span data-ttu-id="d05cd-102">LoadLibraryShim 関数</span><span class="sxs-lookup"><span data-stu-id="d05cd-102">LoadLibraryShim Function</span></span>
<span data-ttu-id="d05cd-103">再頒布可能パッケージ .NET Framework に含まれている、指定したバージョンの DLL を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="d05cd-103">Loads a specified version of a DLL that is included in the .NET Framework redistributable package.</span></span>  
  
 <span data-ttu-id="d05cd-104">この関数は .NET Framework 4 で非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="d05cd-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="d05cd-105">代わりに[ICLRRuntimeInfo:: LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="d05cd-105">Use the [ICLRRuntimeInfo::LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d05cd-106">構文</span><span class="sxs-lookup"><span data-stu-id="d05cd-106">Syntax</span></span>  
  
```cpp  
HRESULT LoadLibraryShim (  
    [in]  LPCWSTR  szDllName,  
    [in]  LPCWSTR  szVersion,  
          LPVOID   pvReserved,  
    [out] HMODULE *phModDll  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d05cd-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d05cd-107">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="d05cd-108">から.NET Framework ライブラリから読み込む DLL の名前を表す、0で終わる文字列です。</span><span class="sxs-lookup"><span data-stu-id="d05cd-108">[in] A zero-terminated string that represents the name of the DLL to be loaded from the .NET Framework library.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="d05cd-109">から読み込む DLL のバージョンを表す、0で終わる文字列。</span><span class="sxs-lookup"><span data-stu-id="d05cd-109">[in] A zero-terminated string that represents the version of the DLL to be loaded.</span></span> <span data-ttu-id="d05cd-110">`szVersion` が null の場合、読み込まれるように選択されたバージョンは、指定された DLL のバージョン4より小さい最新バージョンです。</span><span class="sxs-lookup"><span data-stu-id="d05cd-110">If `szVersion` is null, the version selected for loading is the latest version of the specified DLL that is less than version 4.</span></span> <span data-ttu-id="d05cd-111">つまり、バージョン4以降のすべてのバージョンは、`szVersion` が null の場合は無視され、バージョン4より前のバージョンがインストールされていない場合は、DLL の読み込みに失敗します。</span><span class="sxs-lookup"><span data-stu-id="d05cd-111">That is, all versions equal to or greater than version 4 are ignored if `szVersion` is null, and if no version less than version 4 is installed, the DLL fails to load.</span></span> <span data-ttu-id="d05cd-112">これは、.NET Framework 4 のインストールが、既存のアプリケーションまたはコンポーネントに影響しないようにするためです。</span><span class="sxs-lookup"><span data-stu-id="d05cd-112">This is to ensure that installation of the .NET Framework 4 does not affect pre-existing applications or components.</span></span> <span data-ttu-id="d05cd-113">CLR チームブログの「[インプロセス SxS And Migration クイックスタート](https://go.microsoft.com/fwlink/?LinkId=200329)」のエントリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d05cd-113">See the entry [In-Proc SxS and Migration Quick Start](https://go.microsoft.com/fwlink/?LinkId=200329) in the CLR team blog.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="d05cd-114">将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="d05cd-114">Reserved for future use.</span></span>  
  
 `phModDll`  
 <span data-ttu-id="d05cd-115">入出力モジュールのハンドルへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d05cd-115">[out] A pointer to the handle of the module.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d05cd-116">戻り値</span><span class="sxs-lookup"><span data-stu-id="d05cd-116">Return Value</span></span>  
 <span data-ttu-id="d05cd-117">このメソッドは、次の値に加えて、Winerror.h で定義されている標準のコンポーネントオブジェクトモデル (COM) エラーコードを返します。</span><span class="sxs-lookup"><span data-stu-id="d05cd-117">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="d05cd-118">リターン コード</span><span class="sxs-lookup"><span data-stu-id="d05cd-118">Return code</span></span>|<span data-ttu-id="d05cd-119">説明</span><span class="sxs-lookup"><span data-stu-id="d05cd-119">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="d05cd-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="d05cd-120">S_OK</span></span>|<span data-ttu-id="d05cd-121">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="d05cd-121">The method completed successfully.</span></span>|  
|<span data-ttu-id="d05cd-122">CLR_E_SHIM_RUNTIMELOAD</span><span class="sxs-lookup"><span data-stu-id="d05cd-122">CLR_E_SHIM_RUNTIMELOAD</span></span>|<span data-ttu-id="d05cd-123">`szDllName` を読み込むには、共通言語ランタイム (CLR) を読み込む必要があり、必要なバージョンの CLR を読み込むことができません。</span><span class="sxs-lookup"><span data-stu-id="d05cd-123">Loading `szDllName` requires loading the common language runtime (CLR), and the necessary version of the CLR cannot be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d05cd-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="d05cd-124">Remarks</span></span>  
 <span data-ttu-id="d05cd-125">この関数は、.NET Framework 再頒布可能パッケージに含まれている Dll を読み込むために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d05cd-125">This function is used to load DLLs that are included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="d05cd-126">ユーザーが生成した Dll は読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="d05cd-126">It does not load user-generated DLLs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d05cd-127">.NET Framework バージョン2.0 以降では、Fusion .dll を読み込むと CLR が読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="d05cd-127">Beginning with the .NET Framework version 2.0, loading Fusion.dll causes the CLR to be loaded.</span></span> <span data-ttu-id="d05cd-128">これは、Fusion の関数が、ランタイムによって実装されているラッパーであるためです。</span><span class="sxs-lookup"><span data-stu-id="d05cd-128">This is because the functions in Fusion.dll are now wrappers whose implementations are provided by the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d05cd-129">［要件］</span><span class="sxs-lookup"><span data-stu-id="d05cd-129">Requirements</span></span>  
 <span data-ttu-id="d05cd-130">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d05cd-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d05cd-131">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d05cd-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d05cd-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d05cd-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d05cd-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="d05cd-133">See also</span></span>

- [<span data-ttu-id="d05cd-134">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="d05cd-134">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
