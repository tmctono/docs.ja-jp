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
ms.openlocfilehash: 4f05eb2e6ef31cf1993a623c38bb177f7e3c297e
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2020
ms.locfileid: "75935647"
---
# <a name="gettypelibinfo-function"></a><span data-ttu-id="6366b-102">GetTypeLibInfo 関数</span><span class="sxs-lookup"><span data-stu-id="6366b-102">GetTypeLibInfo Function</span></span>
<span data-ttu-id="6366b-103">指定したタイプライブラリに関する情報を返します。そのためには、その[Tlibattr](/windows/win32/api/oaidl/ns-oaidl-tlibattr)構造体を調べます。</span><span class="sxs-lookup"><span data-stu-id="6366b-103">Returns information about the specified type library by examining its [TLIBATTR](/windows/win32/api/oaidl/ns-oaidl-tlibattr) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6366b-104">構文</span><span class="sxs-lookup"><span data-stu-id="6366b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6366b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6366b-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="6366b-106">からタイプライブラリのファイル名。</span><span class="sxs-lookup"><span data-stu-id="6366b-106">[in] The file name of the type library.</span></span>  
  
 `pTypeLibID`  
 <span data-ttu-id="6366b-107">入出力タイプライブラリの GUID。</span><span class="sxs-lookup"><span data-stu-id="6366b-107">[out] The GUID of the type library.</span></span>  
  
 `pTypeLibLCID`  
 <span data-ttu-id="6366b-108">入出力タイプライブラリのローカライズ ID。</span><span class="sxs-lookup"><span data-stu-id="6366b-108">[out] The localization ID of the type library.</span></span>  
  
 `pTypeLibPlatform`  
 <span data-ttu-id="6366b-109">入出力タイプライブラリのターゲットオペレーティングシステムを識別する[SYSKIND](/windows/win32/api/oaidl/ne-oaidl-syskind)フラグ。</span><span class="sxs-lookup"><span data-stu-id="6366b-109">[out] A [SYSKIND](/windows/win32/api/oaidl/ne-oaidl-syskind) flag that identifies the target operating system for the type library.</span></span> <span data-ttu-id="6366b-110">共通値は SYS_WIN32 と SYS_WIN64 です。</span><span class="sxs-lookup"><span data-stu-id="6366b-110">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pTypeLibMajorVer`  
 <span data-ttu-id="6366b-111">入出力タイプライブラリのメジャーバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="6366b-111">[out] The major version number of the type library.</span></span> <span data-ttu-id="6366b-112">たとえば、バージョン*x.y*の場合、メジャーバージョン番号は*x*になります。</span><span class="sxs-lookup"><span data-stu-id="6366b-112">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `pTypeLibMinorVer`  
 <span data-ttu-id="6366b-113">入出力タイプライブラリのマイナーバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="6366b-113">[out] The minor version number of the type library.</span></span> <span data-ttu-id="6366b-114">たとえば、バージョン*x.y*の場合、マイナーバージョン番号は*y*になります。</span><span class="sxs-lookup"><span data-stu-id="6366b-114">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6366b-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="6366b-115">Remarks</span></span>  
 <span data-ttu-id="6366b-116">`GetTypeLibInfo` 関数は、 [tlbexp.exe (タイプライブラリエクスポーター)](../../tools/tlbexp-exe-type-library-exporter.md)によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="6366b-116">The `GetTypeLibInfo` function is called by the [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md).</span></span> <span data-ttu-id="6366b-117">このツールは、共通言語ランタイム (CLR) アセンブリ内の型を記述するタイプライブラリを生成します。</span><span class="sxs-lookup"><span data-stu-id="6366b-117">This tool generates a type library that describes the types in a common language runtime (CLR) assembly.</span></span>  
  
 <span data-ttu-id="6366b-118">いずれかのパラメーターが null の場合、関数は `E_POINTER`の `HRESULT` を返します。</span><span class="sxs-lookup"><span data-stu-id="6366b-118">If any parameter is null, the function returns an `HRESULT` of `E_POINTER`.</span></span> <span data-ttu-id="6366b-119">それ以外の場合は、 `S_OK`を返します。</span><span class="sxs-lookup"><span data-stu-id="6366b-119">Otherwise, it returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6366b-120">要件</span><span class="sxs-lookup"><span data-stu-id="6366b-120">Requirements</span></span>  
 <span data-ttu-id="6366b-121">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6366b-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6366b-122">**ヘッダー:** Tlf .h</span><span class="sxs-lookup"><span data-stu-id="6366b-122">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="6366b-123">**ライブラリ:** Tlf .lib</span><span class="sxs-lookup"><span data-stu-id="6366b-123">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="6366b-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6366b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6366b-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="6366b-125">See also</span></span>

- [<span data-ttu-id="6366b-126">Tlbexp ヘルパー関数</span><span class="sxs-lookup"><span data-stu-id="6366b-126">Tlbexp Helper Functions</span></span>](index.md)
- [<span data-ttu-id="6366b-127">LoadTypeLibEx 関数</span><span class="sxs-lookup"><span data-stu-id="6366b-127">LoadTypeLibEx Function</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
