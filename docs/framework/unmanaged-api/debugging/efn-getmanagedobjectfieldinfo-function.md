---
title: _EFN_GetManagedObjectFieldInfo 関数
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectFieldInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectFieldInfo
helpviewer_keywords:
- _EFN_GetManagedObjectFieldInfo function [.NET Framework debugging]
ms.assetid: 3b93bcff-62a4-47b2-babc-6bcf4216119a
topic_type:
- apiref
ms.openlocfilehash: 42f7020212dd2db793b7c7d20a15c129157e7261
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860766"
---
# <a name="_efn_getmanagedobjectfieldinfo-function"></a><span data-ttu-id="e8d0d-102">\_EFN\_GetManagedObjectFieldInfo 関数</span><span class="sxs-lookup"><span data-stu-id="e8d0d-102">\_EFN\_GetManagedObjectFieldInfo Function</span></span>
<span data-ttu-id="e8d0d-103">指定したオブジェクト ポインターとフィールド名を使用して、オブジェクトの先頭からフィールドまでのオフセットとフィールドの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="e8d0d-103">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8d0d-104">構文</span><span class="sxs-lookup"><span data-stu-id="e8d0d-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8d0d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e8d0d-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="e8d0d-106">からデバッグクライアントへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e8d0d-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="e8d0d-107">からマネージオブジェクトポインター。</span><span class="sxs-lookup"><span data-stu-id="e8d0d-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="e8d0d-108">szFieldName</span><span class="sxs-lookup"><span data-stu-id="e8d0d-108">szFieldName</span></span>  
 <span data-ttu-id="e8d0d-109">からフィールド名へのマネージオブジェクトポインター。</span><span class="sxs-lookup"><span data-stu-id="e8d0d-109">[in] A managed object pointer to the field name.</span></span>  
  
 `pValue`  
 <span data-ttu-id="e8d0d-110">入出力フィールド値。</span><span class="sxs-lookup"><span data-stu-id="e8d0d-110">[out] The field value.</span></span> <span data-ttu-id="e8d0d-111">このパラメーターには、null を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e8d0d-111">This parameter can be null.</span></span>  
  
 `pOffset`  
 <span data-ttu-id="e8d0d-112">入出力から`objAddr`フィールドへのオフセット。</span><span class="sxs-lookup"><span data-stu-id="e8d0d-112">[out] The offset from `objAddr` to the field.</span></span> <span data-ttu-id="e8d0d-113">このパラメーターには、null を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e8d0d-113">This parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8d0d-114">解説</span><span class="sxs-lookup"><span data-stu-id="e8d0d-114">Remarks</span></span>  
 <span data-ttu-id="e8d0d-115">オフセットが0の場合、オフセットは書き込まれません。</span><span class="sxs-lookup"><span data-stu-id="e8d0d-115">If the offset is 0, no offset is written.</span></span>  
  
 <span data-ttu-id="e8d0d-116">現在コンテキスト内にあるスレッドにマネージコードがない場合、関数は、ファシリティ値が0xa0 でエラーコードが0x1000 の HRESULT SOS_E_NOMANAGEDCODE を返します。</span><span class="sxs-lookup"><span data-stu-id="e8d0d-116">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8d0d-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="e8d0d-117">Requirements</span></span>  
 <span data-ttu-id="e8d0d-118">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8d0d-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8d0d-119">**ヘッダー:** SOS_Stacktrace</span><span class="sxs-lookup"><span data-stu-id="e8d0d-119">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="e8d0d-120">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8d0d-120">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8d0d-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8d0d-121">See also</span></span>

- [<span data-ttu-id="e8d0d-122">デバッグ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="e8d0d-122">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
