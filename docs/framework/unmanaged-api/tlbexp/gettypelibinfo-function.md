---
title: GetTypeLibInfo 関数
ms.date: 03/30/2017
api_name:
- GetTypeLibInfo
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- GetTypeLibInfo
helpviewer_keywords:
- GetTypeLibInfo function [.NET Framework]
ms.assetid: a1c4d165-9bdc-4ca8-940e-292d4ffcc338
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d12cbb66464baba4ee706ccb076764fbf025fc5f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59148539"
---
# <a name="gettypelibinfo-function"></a><span data-ttu-id="c2668-102">GetTypeLibInfo 関数</span><span class="sxs-lookup"><span data-stu-id="c2668-102">GetTypeLibInfo Function</span></span>
<span data-ttu-id="c2668-103">調べることで指定したタイプ ライブラリに関する情報を返します、 [TLIBATTR](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagtlibattr)構造体。</span><span class="sxs-lookup"><span data-stu-id="c2668-103">Returns information about the specified type library by examining its [TLIBATTR](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagtlibattr) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2668-104">構文</span><span class="sxs-lookup"><span data-stu-id="c2668-104">Syntax</span></span>  
  
```  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2668-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c2668-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="c2668-106">[in]タイプ ライブラリのファイル名。</span><span class="sxs-lookup"><span data-stu-id="c2668-106">[in] The file name of the type library.</span></span>  
  
 `pTypeLibID`  
 <span data-ttu-id="c2668-107">[out]タイプ ライブラリの GUID です。</span><span class="sxs-lookup"><span data-stu-id="c2668-107">[out] The GUID of the type library.</span></span>  
  
 `pTypeLibLCID`  
 <span data-ttu-id="c2668-108">[out]タイプ ライブラリのローカリゼーション ID。</span><span class="sxs-lookup"><span data-stu-id="c2668-108">[out] The localization ID of the type library.</span></span>  
  
 `pTypeLibPlatform`  
 <span data-ttu-id="c2668-109">[out]A [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind)タイプ ライブラリの対象のオペレーティング システムを識別するフラグ。</span><span class="sxs-lookup"><span data-stu-id="c2668-109">[out] A [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) flag that identifies the target operating system for the type library.</span></span> <span data-ttu-id="c2668-110">一般的な値は SYS_WIN32 および SYS_WIN64 です。</span><span class="sxs-lookup"><span data-stu-id="c2668-110">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pTypeLibMajorVer`  
 <span data-ttu-id="c2668-111">[out]タイプ ライブラリのメジャー バージョン番号。</span><span class="sxs-lookup"><span data-stu-id="c2668-111">[out] The major version number of the type library.</span></span> <span data-ttu-id="c2668-112">たとえば、バージョン*x.y*、メジャー バージョン番号は*x*します。</span><span class="sxs-lookup"><span data-stu-id="c2668-112">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `pTypeLibMinorVer`  
 <span data-ttu-id="c2668-113">[out]タイプ ライブラリのマイナー バージョン番号。</span><span class="sxs-lookup"><span data-stu-id="c2668-113">[out] The minor version number of the type library.</span></span> <span data-ttu-id="c2668-114">たとえば、バージョン*x.y*、マイナー バージョン番号は*y*します。</span><span class="sxs-lookup"><span data-stu-id="c2668-114">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2668-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="c2668-115">Remarks</span></span>  
 <span data-ttu-id="c2668-116">`GetTypeLibInfo`関数を呼び出して、 [Tlbexp.exe (タイプ ライブラリ エクスポーター)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)します。</span><span class="sxs-lookup"><span data-stu-id="c2668-116">The `GetTypeLibInfo` function is called by the [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md).</span></span> <span data-ttu-id="c2668-117">このツールは、共通言語ランタイム (CLR) アセンブリで型を記述するタイプ ライブラリを生成します。</span><span class="sxs-lookup"><span data-stu-id="c2668-117">This tool generates a type library that describes the types in a common language runtime (CLR) assembly.</span></span>  
  
 <span data-ttu-id="c2668-118">任意のパラメーターが null 関数を返します、`HRESULT`の`E_POINTER`します。</span><span class="sxs-lookup"><span data-stu-id="c2668-118">If any parameter is null, the function returns an `HRESULT` of `E_POINTER`.</span></span> <span data-ttu-id="c2668-119">それ以外の場合は、 `S_OK`を返します。</span><span class="sxs-lookup"><span data-stu-id="c2668-119">Otherwise, it returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2668-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="c2668-120">Requirements</span></span>  
 <span data-ttu-id="c2668-121">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2668-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2668-122">**ヘッダー:** TlbRef.h</span><span class="sxs-lookup"><span data-stu-id="c2668-122">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="c2668-123">**ライブラリ:** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="c2668-123">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="c2668-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2668-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2668-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2668-125">See also</span></span>

- [<span data-ttu-id="c2668-126">Tlbexp ヘルパー関数</span><span class="sxs-lookup"><span data-stu-id="c2668-126">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [<span data-ttu-id="c2668-127">LoadTypeLibEx 関数</span><span class="sxs-lookup"><span data-stu-id="c2668-127">LoadTypeLibEx Function</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
