---
title: ICLRDataTarget3::GetExceptionThreadID メソッド
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetExceptionThreadID
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 307d6ac7-4a86-45f3-999d-6b47004a68f2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6503efbaa4db89b243a85b69f60b091c6bb49ef
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59215301"
---
# <a name="iclrdatatarget3getexceptionthreadid-method"></a><span data-ttu-id="78397-102">ICLRDataTarget3::GetExceptionThreadID メソッド</span><span class="sxs-lookup"><span data-stu-id="78397-102">ICLRDataTarget3::GetExceptionThreadID Method</span></span>
<span data-ttu-id="78397-103">例外をスローしたスレッドの ID を取得するために、共通言語ランタイム (CLR) データ アクセス サービスによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="78397-103">Called by the common language runtime (CLR) data access services to get the ID of the thread that threw the exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78397-104">構文</span><span class="sxs-lookup"><span data-stu-id="78397-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionThreadID(  
    [out] ULONG32* threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78397-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="78397-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="78397-106">[out] 例外をスローしたスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="78397-106">[out] The ID of the thread that threw the exception.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="78397-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="78397-107">Return Value</span></span>  
 <span data-ttu-id="78397-108">戻り値は、成功の場合は `S_OK` で、失敗の場合は `HRESULT` コードです。</span><span class="sxs-lookup"><span data-stu-id="78397-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="78397-109">次が `HRESULT` コードに含まれることはありますが、限定されているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="78397-109">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="78397-110">リターン コード</span><span class="sxs-lookup"><span data-stu-id="78397-110">Return code</span></span>|<span data-ttu-id="78397-111">説明</span><span class="sxs-lookup"><span data-stu-id="78397-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="78397-112">メソッドが成功しました。</span><span class="sxs-lookup"><span data-stu-id="78397-112">Method succeeded.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="78397-113">例外の有効なスレッド ID を見つけることができませんでした。</span><span class="sxs-lookup"><span data-stu-id="78397-113">Could not find a valid thread ID for the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78397-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="78397-114">Remarks</span></span>  
 <span data-ttu-id="78397-115">このメソッドは、デバッグ アプリケーションの作成者によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="78397-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78397-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="78397-116">Requirements</span></span>  
 <span data-ttu-id="78397-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="78397-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78397-118">**ヘッダー:** ClrData.idl、ClrData.h</span><span class="sxs-lookup"><span data-stu-id="78397-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="78397-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78397-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78397-120">**.NET Framework のバージョン:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="78397-120">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78397-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="78397-121">See also</span></span>

- [<span data-ttu-id="78397-122">ICLRDataTarget3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="78397-122">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)
- [<span data-ttu-id="78397-123">GetExceptionContextRecord メソッド</span><span class="sxs-lookup"><span data-stu-id="78397-123">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)
- [<span data-ttu-id="78397-124">GetExceptionRecord メソッド</span><span class="sxs-lookup"><span data-stu-id="78397-124">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)
