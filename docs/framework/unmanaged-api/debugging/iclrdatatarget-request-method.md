---
title: ICLRDataTarget::Request メソッド
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.Request
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::Request
helpviewer_keywords:
- ICLRDataTarget::Request method [.NET Framework debugging]
- Request method [.NET Framework debugging]
ms.assetid: 4723bd1c-eddb-4ed2-897a-010024a47e01
topic_type:
- apiref
ms.openlocfilehash: 336ba38bc80fcb2649a12c78691e52c5e4d70bfe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179110"
---
# <a name="iclrdatatargetrequest-method"></a><span data-ttu-id="544f3-102">ICLRDataTarget::Request メソッド</span><span class="sxs-lookup"><span data-stu-id="544f3-102">ICLRDataTarget::Request Method</span></span>
<span data-ttu-id="544f3-103">共通言語ランタイム (CLR) データ アクセス サービスによって呼び出され、実装で定義されている操作を要求します。</span><span class="sxs-lookup"><span data-stu-id="544f3-103">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="544f3-104">構文</span><span class="sxs-lookup"><span data-stu-id="544f3-104">Syntax</span></span>  
  
```cpp  
HRESULT Request (  
    [in] ULONG32            reqCode,  
    [in] ULONG32            inBufferSize,  
    [in, size_is(inBufferSize)]
        BYTE                *inBuffer,  
    [in] ULONG32            outBufferSize,  
    [out, size_is(outBufferSize)]
        BYTE                *outBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="544f3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="544f3-105">Parameters</span></span>  
 `reqCode`  
 <span data-ttu-id="544f3-106">[in]ユーザー定義。</span><span class="sxs-lookup"><span data-stu-id="544f3-106">[in] User-defined.</span></span>  
  
 `inBufferSize`  
 <span data-ttu-id="544f3-107">[in]入力要求に使用される入力バッファーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="544f3-107">[in] The size of the input buffer, which is used for the incoming request.</span></span>  
  
 `inBuffer`  
 <span data-ttu-id="544f3-108">[in]要求を含むバッファー。</span><span class="sxs-lookup"><span data-stu-id="544f3-108">[in] A buffer containing the request.</span></span>  
  
 `outBufferSize`  
 <span data-ttu-id="544f3-109">[in]応答に使用される出力バッファーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="544f3-109">[in] The size of the output buffer, which is used for the response.</span></span>  
  
 `outBuffer`  
 <span data-ttu-id="544f3-110">[アウト]応答を含むバッファー。</span><span class="sxs-lookup"><span data-stu-id="544f3-110">[out] A Buffer containing the response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="544f3-111">解説</span><span class="sxs-lookup"><span data-stu-id="544f3-111">Remarks</span></span>  
 <span data-ttu-id="544f3-112">この`Request`メソッドは、指定されていないカスタム操作の追加を容易にします。</span><span class="sxs-lookup"><span data-stu-id="544f3-112">The `Request` method facilitates the addition of unspecified custom operations.</span></span> <span data-ttu-id="544f3-113">つまり、このメソッドは、インターフェイス定義のリビジョンを必要とせずに機能拡張を提供します。</span><span class="sxs-lookup"><span data-stu-id="544f3-113">That is, this method provides extensibility without requiring revision of the interface definition.</span></span>  
  
 <span data-ttu-id="544f3-114">このメソッドは、デバッグ アプリケーションの作成者によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="544f3-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="544f3-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="544f3-115">Requirements</span></span>  
 <span data-ttu-id="544f3-116">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="544f3-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="544f3-117">**ヘッダー:** をします。</span><span class="sxs-lookup"><span data-stu-id="544f3-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="544f3-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="544f3-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="544f3-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="544f3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="544f3-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="544f3-120">See also</span></span>

- [<span data-ttu-id="544f3-121">ICLRDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="544f3-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
