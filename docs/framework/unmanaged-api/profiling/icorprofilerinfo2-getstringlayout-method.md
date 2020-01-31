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
ms.openlocfilehash: 537840ac03b4136682b78cb964950ab5670a7d7e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868617"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a><span data-ttu-id="820ff-102">ICorProfilerInfo2::GetStringLayout メソッド</span><span class="sxs-lookup"><span data-stu-id="820ff-102">ICorProfilerInfo2::GetStringLayout Method</span></span>
<span data-ttu-id="820ff-103">文字列オブジェクトのレイアウトに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="820ff-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="820ff-104">このメソッドは .NET Framework 4 では非推奨とされており、 [ICorProfilerInfo3:: GetStringLayout2](icorprofilerinfo3-getstringlayout2-method.md)メソッドに置き換えられています。</span><span class="sxs-lookup"><span data-stu-id="820ff-104">This method is deprecated in the .NET Framework 4, and is superseded by the [ICorProfilerInfo3::GetStringLayout2](icorprofilerinfo3-getstringlayout2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="820ff-105">構文</span><span class="sxs-lookup"><span data-stu-id="820ff-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="820ff-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="820ff-106">Parameters</span></span>  
 `pBufferLengthOffset`  
 <span data-ttu-id="820ff-107">入出力文字列の長さを格納する、`ObjectID` ポインターを基準とした位置のオフセットを指すポインター。</span><span class="sxs-lookup"><span data-stu-id="820ff-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string.</span></span> <span data-ttu-id="820ff-108">長さは `DWORD`として格納されます。</span><span class="sxs-lookup"><span data-stu-id="820ff-108">The length is stored as a `DWORD`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="820ff-109">このパラメーターは、バッファーの長さではなく、文字列自体の長さを返します。</span><span class="sxs-lookup"><span data-stu-id="820ff-109">This parameter returns the length of the string itself, not the length of the buffer.</span></span> <span data-ttu-id="820ff-110">バッファーの長さは使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="820ff-110">The length of the buffer is no longer available.</span></span>  
  
 `PStringLengthOffset`  
 <span data-ttu-id="820ff-111">入出力文字列自体の長さを格納する、`ObjectID` ポインターを基準とした位置のオフセットを指すポインター。</span><span class="sxs-lookup"><span data-stu-id="820ff-111">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="820ff-112">長さは `DWORD`として格納されます。</span><span class="sxs-lookup"><span data-stu-id="820ff-112">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="820ff-113">入出力ワイド文字の文字列を格納する、`ObjectID` ポインターを基準としたバッファーのオフセットへのポインター。</span><span class="sxs-lookup"><span data-stu-id="820ff-113">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, that stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="820ff-114">コメント</span><span class="sxs-lookup"><span data-stu-id="820ff-114">Remarks</span></span>  
 <span data-ttu-id="820ff-115">`GetStringLayout` メソッドは、次のが格納されている場所のオフセットを `ObjectID` ポインターを基準として取得します。</span><span class="sxs-lookup"><span data-stu-id="820ff-115">The `GetStringLayout` method gets the offsets, relative to the `ObjectID` pointer, of the locations in which the following are stored:</span></span>  
  
- <span data-ttu-id="820ff-116">文字列のバッファーの長さ。</span><span class="sxs-lookup"><span data-stu-id="820ff-116">The length of the string's buffer.</span></span>  
  
- <span data-ttu-id="820ff-117">文字列自体の長さ。</span><span class="sxs-lookup"><span data-stu-id="820ff-117">The length of the string itself.</span></span>  
  
- <span data-ttu-id="820ff-118">ワイド文字の実際の文字列を格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="820ff-118">The buffer that contains the actual string of wide characters.</span></span>  
  
 <span data-ttu-id="820ff-119">文字列は null で終わる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="820ff-119">Strings may be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="820ff-120">要件</span><span class="sxs-lookup"><span data-stu-id="820ff-120">Requirements</span></span>  
 <span data-ttu-id="820ff-121">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="820ff-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="820ff-122">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="820ff-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="820ff-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="820ff-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="820ff-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="820ff-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="820ff-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="820ff-125">See also</span></span>

- [<span data-ttu-id="820ff-126">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="820ff-126">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="820ff-127">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="820ff-127">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
