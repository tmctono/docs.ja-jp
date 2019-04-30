---
title: ICorProfilerInfo3::GetRuntimeInformation メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetRuntimeInformation Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetRuntimeInformation
helpviewer_keywords:
- GetRuntimeInformation method [.NET Framework profiling]
- ICorProfilerInfo3::GetRuntimeInformation method [.NET Framework profiling]
ms.assetid: 4400fb8c-0407-4791-8557-f011fd2aee51
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a13e3e525c7f019e7dc49111b88ac374345830af
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000598"
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a><span data-ttu-id="8e091-102">ICorProfilerInfo3::GetRuntimeInformation メソッド</span><span class="sxs-lookup"><span data-stu-id="8e091-102">ICorProfilerInfo3::GetRuntimeInformation Method</span></span>
<span data-ttu-id="8e091-103">プロファイリングされている共通言語ランタイム (CLR) のバージョンについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8e091-103">Provides version information about the common language runtime (CLR) that is being profiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e091-104">構文</span><span class="sxs-lookup"><span data-stu-id="8e091-104">Syntax</span></span>  
  
```  
HRESULT GetRuntimeInformation(  
       [out] USHORT *pClrInstanceId,  
       [out] COR_PRF_RUNTIME_TYPE *pRuntimeType,  
       [out] USHORT *pMajorVersion,  
       [out] USHORT *pMinorVersion,  
       [out] USHORT *pBuildNumber,  
       [out] USHORT *pQFEVersion,  
       [in]  ULONG  cchVersionString,  
       [out] ULONG  *pcchVersionString,  
       [out, size_is(cchVersionString), length_is(*pcchVersionString)]  
                   WCHAR  szVersionString[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e091-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8e091-105">Parameters</span></span>  
 `pClrInstanceId`  
 <span data-ttu-id="8e091-106">[out]プロセスで実行中の CLR インスタンスの担当者の ID。</span><span class="sxs-lookup"><span data-stu-id="8e091-106">[out] The representative ID of a running CLR instance in a process.</span></span> <span data-ttu-id="8e091-107">これと同じ、 `ClrInstanceID` Windows (ETW) のスタートアップ イベント トレーシングのイベントをレポートすることです。</span><span class="sxs-lookup"><span data-stu-id="8e091-107">This is the same as the `ClrInstanceID` that the event tracing for Windows (ETW) startup event reports.</span></span>  
  
 `pRuntimeType`  
 <span data-ttu-id="8e091-108">[out]ランタイム型。</span><span class="sxs-lookup"><span data-stu-id="8e091-108">[out] The runtime type.</span></span> <span data-ttu-id="8e091-109">このパラメーターを返します`COR_PRF_DESKTOP_CLR`、CLR のデスクトップ バージョンのまたは`COR_PRF_CORE_CLR`Silverlight で使用されている CLR の core バージョン。</span><span class="sxs-lookup"><span data-stu-id="8e091-109">This parameter returns `COR_PRF_DESKTOP_CLR` for the desktop version of the CLR, or `COR_PRF_CORE_CLR` for the core version of the CLR used in Silverlight.</span></span>  
  
 `pMajorVersion`  
 <span data-ttu-id="8e091-110">[out]CLR のメジャー バージョン番号。</span><span class="sxs-lookup"><span data-stu-id="8e091-110">[out] The major version number of the CLR.</span></span>  
  
 `pMinorVersion`  
 <span data-ttu-id="8e091-111">[out]CLR のマイナー バージョン番号。</span><span class="sxs-lookup"><span data-stu-id="8e091-111">[out] The minor version number of the CLR.</span></span>  
  
 `pBuildVersion`  
 <span data-ttu-id="8e091-112">[out]CLR のビルド バージョン番号。</span><span class="sxs-lookup"><span data-stu-id="8e091-112">[out] The build version number of the CLR.</span></span>  
  
 `pQFEVersion`  
 <span data-ttu-id="8e091-113">[out]ソフトウェア更新プログラムに関連付けられている CLR のバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="8e091-113">[out] The version number of the CLR that is associated with a software update.</span></span>  
  
 `cchVersionString`  
 <span data-ttu-id="8e091-114">[in]バッファーの文字の長さを`szVersionString`を指します。</span><span class="sxs-lookup"><span data-stu-id="8e091-114">[in] The length, in characters, of the buffer that `szVersionString` points to.</span></span>  
  
 `pcchVersionString`  
 <span data-ttu-id="8e091-115">[out]長さを文字単位の`szVersionString`します。</span><span class="sxs-lookup"><span data-stu-id="8e091-115">[out] The length, in characters, of `szVersionString`.</span></span>  
  
 `szVersionString`  
 <span data-ttu-id="8e091-116">[out]CLR バージョン文字列です。</span><span class="sxs-lookup"><span data-stu-id="8e091-116">[out] The CLR version string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e091-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="8e091-117">Remarks</span></span>  
 <span data-ttu-id="8e091-118">任意のパラメーターに null を渡すことがあります。</span><span class="sxs-lookup"><span data-stu-id="8e091-118">You may pass null for any parameter.</span></span> <span data-ttu-id="8e091-119">ただし、 `pcchVersionString` null にすることはできませんしない限り、`szVersionString`も null です。</span><span class="sxs-lookup"><span data-stu-id="8e091-119">However, `pcchVersionString` cannot be null unless `szVersionString` is also null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e091-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="8e091-120">Requirements</span></span>  
 <span data-ttu-id="8e091-121">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e091-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e091-122">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8e091-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8e091-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e091-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e091-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e091-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e091-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e091-125">See also</span></span>

- [<span data-ttu-id="8e091-126">ICorProfilerInfo3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8e091-126">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="8e091-127">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="8e091-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="8e091-128">プロファイル</span><span class="sxs-lookup"><span data-stu-id="8e091-128">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
