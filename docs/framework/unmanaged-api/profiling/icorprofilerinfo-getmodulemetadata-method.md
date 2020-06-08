---
title: ICorProfilerInfo::GetModuleMetaData メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetModuleMetaData
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetModuleMetaData
helpviewer_keywords:
- GetModuleMetaData method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleMetaData method [.NET Framework profiling]
ms.assetid: 7a439d92-348a-44dd-b60f-cad7cba56379
topic_type:
- apiref
ms.openlocfilehash: 62b34128be99ce7750d45e6c19e26bef7fcc98c5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502952"
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a><span data-ttu-id="5278e-102">ICorProfilerInfo::GetModuleMetaData メソッド</span><span class="sxs-lookup"><span data-stu-id="5278e-102">ICorProfilerInfo::GetModuleMetaData Method</span></span>
<span data-ttu-id="5278e-103">指定したモジュールにマップされるメタデータインターフェイスインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="5278e-103">Gets a metadata interface instance that maps to the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5278e-104">構文</span><span class="sxs-lookup"><span data-stu-id="5278e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleMetaData(  
    [in]  ModuleID moduleId,  
    [in]  DWORD    dwOpenFlags,  
    [in]  REFIID   riid,  
    [out] IUnknown **ppOut);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5278e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5278e-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="5278e-106">からインターフェイスインスタンスのマップ先となるモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="5278e-106">[in] The ID of the module to which the interface instance will be mapped.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="5278e-107">からマニフェストファイルを開くモードを指定する[Coropenflags](../metadata/coropenflags-enumeration.md)列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="5278e-107">[in] A value of the [CorOpenFlags](../metadata/coropenflags-enumeration.md) enumeration that specifies the mode for opening manifest files.</span></span> <span data-ttu-id="5278e-108">、、 `ofRead` およびの各 `ofWrite` ビットのみ `ofNoTransform` が有効です。</span><span class="sxs-lookup"><span data-stu-id="5278e-108">Only the `ofRead`, `ofWrite` and `ofNoTransform` bits are valid.</span></span>  
  
 `riid`  
 <span data-ttu-id="5278e-109">からインスタンスを取得するメタデータインターフェイスの参照 ID (GUID)。</span><span class="sxs-lookup"><span data-stu-id="5278e-109">[in] The reference ID (GUID) of the metadata interface whose instance will be retrieved.</span></span> <span data-ttu-id="5278e-110">インターフェイスの一覧については、「[メタデータインターフェイス](../metadata/metadata-interfaces.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5278e-110">See [Metadata Interfaces](../metadata/metadata-interfaces.md) for a list of the interfaces.</span></span>  
  
 `ppOut`  
 <span data-ttu-id="5278e-111">入出力メタデータインターフェイスインスタンスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5278e-111">[out] A pointer to the address of the metadata interface instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5278e-112">解説</span><span class="sxs-lookup"><span data-stu-id="5278e-112">Remarks</span></span>  
 <span data-ttu-id="5278e-113">メタデータを読み取り/書き込みモードで開くように要求することはできますが、メタデータに対して行われた変更はコンパイラからのものとして最適化できないため、プログラムのメタデータ実行が遅くなります。</span><span class="sxs-lookup"><span data-stu-id="5278e-113">You may ask for the metadata to be opened in read/write mode, but this will result in slower metadata execution of the program, because changes made to the metadata cannot be optimized as they were from the compiler.</span></span>  
  
 <span data-ttu-id="5278e-114">一部のモジュール (リソースモジュールなど) にはメタデータがありません。</span><span class="sxs-lookup"><span data-stu-id="5278e-114">Some modules (such as resource modules) have no metadata.</span></span> <span data-ttu-id="5278e-115">このような場合、 `GetModuleMetaData` は S_FALSE の HRESULT 値を返し、\* では null を返し `ppOut` ます。</span><span class="sxs-lookup"><span data-stu-id="5278e-115">In those cases, `GetModuleMetaData` will return an HRESULT value of S_FALSE, and a null in \*`ppOut`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5278e-116">要件</span><span class="sxs-lookup"><span data-stu-id="5278e-116">Requirements</span></span>  
 <span data-ttu-id="5278e-117">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5278e-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5278e-118">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5278e-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5278e-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5278e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5278e-120">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5278e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5278e-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="5278e-121">See also</span></span>

- [<span data-ttu-id="5278e-122">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5278e-122">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
