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
ms.openlocfilehash: 5e7fd2f277a9c3d8410020a53d348456ef9deffb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73111906"
---
# <a name="iclrdatatarget3getexceptionthreadid-method"></a><span data-ttu-id="01cdb-102">ICLRDataTarget3::GetExceptionThreadID メソッド</span><span class="sxs-lookup"><span data-stu-id="01cdb-102">ICLRDataTarget3::GetExceptionThreadID Method</span></span>
<span data-ttu-id="01cdb-103">例外をスローしたスレッドの ID を取得するために、共通言語ランタイム (CLR) データ アクセス サービスによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="01cdb-103">Called by the common language runtime (CLR) data access services to get the ID of the thread that threw the exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01cdb-104">構文</span><span class="sxs-lookup"><span data-stu-id="01cdb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionThreadID(  
    [out] ULONG32* threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01cdb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="01cdb-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="01cdb-106">[out] 例外をスローしたスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="01cdb-106">[out] The ID of the thread that threw the exception.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01cdb-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="01cdb-107">Return Value</span></span>  
 <span data-ttu-id="01cdb-108">戻り値は、成功の場合は `S_OK` で、失敗の場合は `HRESULT` コードです。</span><span class="sxs-lookup"><span data-stu-id="01cdb-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="01cdb-109">次が `HRESULT` コードに含まれることはありますが、限定されているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="01cdb-109">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="01cdb-110">リターン コード</span><span class="sxs-lookup"><span data-stu-id="01cdb-110">Return code</span></span>|<span data-ttu-id="01cdb-111">説明</span><span class="sxs-lookup"><span data-stu-id="01cdb-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="01cdb-112">メソッドが成功しました。</span><span class="sxs-lookup"><span data-stu-id="01cdb-112">Method succeeded.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="01cdb-113">例外の有効なスレッド ID を見つけることができませんでした。</span><span class="sxs-lookup"><span data-stu-id="01cdb-113">Could not find a valid thread ID for the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01cdb-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="01cdb-114">Remarks</span></span>  
 <span data-ttu-id="01cdb-115">このメソッドは、デバッグ アプリケーションの作成者によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="01cdb-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01cdb-116">［要件］</span><span class="sxs-lookup"><span data-stu-id="01cdb-116">Requirements</span></span>  
 <span data-ttu-id="01cdb-117">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01cdb-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01cdb-118">**ヘッダー:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="01cdb-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="01cdb-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01cdb-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01cdb-120">**.NET Framework のバージョン:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="01cdb-120">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01cdb-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="01cdb-121">See also</span></span>

- [<span data-ttu-id="01cdb-122">ICLRDataTarget3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="01cdb-122">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)
- [<span data-ttu-id="01cdb-123">GetExceptionContextRecord メソッド</span><span class="sxs-lookup"><span data-stu-id="01cdb-123">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)
- [<span data-ttu-id="01cdb-124">GetExceptionRecord メソッド</span><span class="sxs-lookup"><span data-stu-id="01cdb-124">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)
