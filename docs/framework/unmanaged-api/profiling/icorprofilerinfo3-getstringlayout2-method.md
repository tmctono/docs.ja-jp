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
ms.openlocfilehash: 1542573cbba2ffe407dd78eeb34e0a6e43c4d9a7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496694"
---
# <a name="icorprofilerinfo3getstringlayout2-method"></a><span data-ttu-id="ae8aa-102">ICorProfilerInfo3::GetStringLayout2 メソッド</span><span class="sxs-lookup"><span data-stu-id="ae8aa-102">ICorProfilerInfo3::GetStringLayout2 Method</span></span>
<span data-ttu-id="ae8aa-103">文字列オブジェクトのレイアウトに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="ae8aa-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="ae8aa-104">このメソッドは、 [icorprofilerinfo 2::getstringlayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="ae8aa-104">This method supersedes the [ICorProfilerInfo2::GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae8aa-105">構文</span><span class="sxs-lookup"><span data-stu-id="ae8aa-105">Syntax</span></span>  
  
```  
HRESULT GetStringLayout2(  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae8aa-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ae8aa-106">Parameters</span></span>  
 `pStringLengthOffset`  
 <span data-ttu-id="ae8aa-107">[out]相対の場所のオフセットへのポインター、`ObjectID`文字列自体の長さを格納するポインター。</span><span class="sxs-lookup"><span data-stu-id="ae8aa-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="ae8aa-108">長さが格納されている、`DWORD`します。</span><span class="sxs-lookup"><span data-stu-id="ae8aa-108">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="ae8aa-109">[out]バッファーの相対オフセットへのポインター、`ObjectID`ポインターで、ワイド文字の文字列を格納します。</span><span class="sxs-lookup"><span data-stu-id="ae8aa-109">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, which stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae8aa-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="ae8aa-110">Remarks</span></span>  
 <span data-ttu-id="ae8aa-111">文字列は、null で終わるができない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ae8aa-111">Strings may or may not be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae8aa-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="ae8aa-112">Requirements</span></span>  
 <span data-ttu-id="ae8aa-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae8aa-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae8aa-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ae8aa-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ae8aa-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae8aa-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae8aa-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae8aa-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae8aa-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae8aa-117">See also</span></span>
- [<span data-ttu-id="ae8aa-118">ICorProfilerInfo3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ae8aa-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="ae8aa-119">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="ae8aa-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
