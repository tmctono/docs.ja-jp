---
title: ICorProfilerInfo3::GetStringLayout2 メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetStringLayout2 Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetStringLayout2
helpviewer_keywords:
- ICorProfilerInfo3::GetStringLayout2 method [.NET Framework profiling]
- GetStringLayout2 method [.NET Framework profiling]
ms.assetid: 1a268496-ee51-4d84-8700-ee56fd0c499d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1ac724db000f84e37995a34e808d3df4b1e7a960
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765410"
---
# <a name="icorprofilerinfo3getstringlayout2-method"></a><span data-ttu-id="0346f-102">ICorProfilerInfo3::GetStringLayout2 メソッド</span><span class="sxs-lookup"><span data-stu-id="0346f-102">ICorProfilerInfo3::GetStringLayout2 Method</span></span>
<span data-ttu-id="0346f-103">文字列オブジェクトのレイアウトに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="0346f-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="0346f-104">このメソッドは、 [icorprofilerinfo 2::getstringlayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="0346f-104">This method supersedes the [ICorProfilerInfo2::GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0346f-105">構文</span><span class="sxs-lookup"><span data-stu-id="0346f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringLayout2(  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0346f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0346f-106">Parameters</span></span>  
 `pStringLengthOffset`  
 <span data-ttu-id="0346f-107">[out]相対の場所のオフセットへのポインター、`ObjectID`文字列自体の長さを格納するポインター。</span><span class="sxs-lookup"><span data-stu-id="0346f-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="0346f-108">長さが格納されている、`DWORD`します。</span><span class="sxs-lookup"><span data-stu-id="0346f-108">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="0346f-109">[out]バッファーの相対オフセットへのポインター、`ObjectID`ポインターで、ワイド文字の文字列を格納します。</span><span class="sxs-lookup"><span data-stu-id="0346f-109">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, which stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0346f-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="0346f-110">Remarks</span></span>  
 <span data-ttu-id="0346f-111">文字列は、null で終わるができない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0346f-111">Strings may or may not be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0346f-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="0346f-112">Requirements</span></span>  
 <span data-ttu-id="0346f-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0346f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0346f-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0346f-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0346f-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0346f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0346f-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0346f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0346f-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="0346f-117">See also</span></span>

- [<span data-ttu-id="0346f-118">ICorProfilerInfo3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0346f-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="0346f-119">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="0346f-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
