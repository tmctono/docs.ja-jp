---
title: ICorProfilerInfo2::GetStringLayout メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStringLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStringLayout
helpviewer_keywords:
- GetStringLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetStringLayout method [.NET Framework profiling]
ms.assetid: 43189651-a535-4803-a1d1-f1c427ace2ca
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: faa5ecf63ac3795a58369d94f9fb15f853edb576
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490702"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a><span data-ttu-id="12c08-102">ICorProfilerInfo2::GetStringLayout メソッド</span><span class="sxs-lookup"><span data-stu-id="12c08-102">ICorProfilerInfo2::GetStringLayout Method</span></span>
<span data-ttu-id="12c08-103">文字列オブジェクトのレイアウトに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="12c08-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="12c08-104">このメソッドは、.NET Framework 4 では非推奨し、は置き換えられて、 [icorprofilerinfo 3::getstringlayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="12c08-104">This method is deprecated in the .NET Framework 4, and is superseded by the [ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12c08-105">構文</span><span class="sxs-lookup"><span data-stu-id="12c08-105">Syntax</span></span>  
  
```  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12c08-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="12c08-106">Parameters</span></span>  
 `pBufferLengthOffset`  
 <span data-ttu-id="12c08-107">[out]相対の場所のオフセットへのポインター、`ObjectID`ポインターは、文字列の長さを格納します。</span><span class="sxs-lookup"><span data-stu-id="12c08-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string.</span></span> <span data-ttu-id="12c08-108">長さが格納されている、`DWORD`します。</span><span class="sxs-lookup"><span data-stu-id="12c08-108">The length is stored as a `DWORD`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12c08-109">このパラメーターは、バッファーの長さではなく、文字列、自体の長さを返します。</span><span class="sxs-lookup"><span data-stu-id="12c08-109">This parameter returns the length of the string itself, not the length of the buffer.</span></span> <span data-ttu-id="12c08-110">バッファーの長さは使用できなくします。</span><span class="sxs-lookup"><span data-stu-id="12c08-110">The length of the buffer is no longer available.</span></span>  
  
 `PStringLengthOffset`  
 <span data-ttu-id="12c08-111">[out]相対の場所のオフセットへのポインター、`ObjectID`文字列自体の長さを格納するポインター。</span><span class="sxs-lookup"><span data-stu-id="12c08-111">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="12c08-112">長さが格納されている、`DWORD`します。</span><span class="sxs-lookup"><span data-stu-id="12c08-112">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="12c08-113">[out]バッファーの相対オフセットへのポインター、 `ObjectID` 、ワイド文字の文字列を格納するポインター。</span><span class="sxs-lookup"><span data-stu-id="12c08-113">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, that stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12c08-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="12c08-114">Remarks</span></span>  
 <span data-ttu-id="12c08-115">`GetStringLayout`メソッドに関連する、オフセットを取得する、`ObjectID`ポインターは、次が格納されている場所の。</span><span class="sxs-lookup"><span data-stu-id="12c08-115">The `GetStringLayout` method gets the offsets, relative to the `ObjectID` pointer, of the locations in which the following are stored:</span></span>  
  
- <span data-ttu-id="12c08-116">文字列のバッファーの長さ。</span><span class="sxs-lookup"><span data-stu-id="12c08-116">The length of the string's buffer.</span></span>  
  
- <span data-ttu-id="12c08-117">文字列自体の長さ。</span><span class="sxs-lookup"><span data-stu-id="12c08-117">The length of the string itself.</span></span>  
  
- <span data-ttu-id="12c08-118">ワイド文字の実際の文字列を格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="12c08-118">The buffer that contains the actual string of wide characters.</span></span>  
  
 <span data-ttu-id="12c08-119">文字列には、null で終わる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="12c08-119">Strings may be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12c08-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="12c08-120">Requirements</span></span>  
 <span data-ttu-id="12c08-121">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="12c08-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12c08-122">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="12c08-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="12c08-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12c08-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12c08-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12c08-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12c08-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="12c08-125">See also</span></span>

- [<span data-ttu-id="12c08-126">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="12c08-126">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="12c08-127">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="12c08-127">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
