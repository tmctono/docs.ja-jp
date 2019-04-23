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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e7d031d4a4f4e67134f4b88f3e3ff47316ce3b5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183145"
---
# <a name="efngetmanagedobjectfieldinfo-function"></a><span data-ttu-id="a99ca-102">_EFN_GetManagedObjectFieldInfo 関数</span><span class="sxs-lookup"><span data-stu-id="a99ca-102">_EFN_GetManagedObjectFieldInfo Function</span></span>
<span data-ttu-id="a99ca-103">指定したオブジェクト ポインターとフィールド名を使用して、オブジェクトの先頭からフィールドまでのオフセットとフィールドの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="a99ca-103">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a99ca-104">構文</span><span class="sxs-lookup"><span data-stu-id="a99ca-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a99ca-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a99ca-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="a99ca-106">[in]デバッグ クライアントへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a99ca-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="a99ca-107">[in]マネージ オブジェクトのポインター。</span><span class="sxs-lookup"><span data-stu-id="a99ca-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="a99ca-108">szFieldName</span><span class="sxs-lookup"><span data-stu-id="a99ca-108">szFieldName</span></span>  
 <span data-ttu-id="a99ca-109">[in]フィールド名にマネージ オブジェクトのポインター。</span><span class="sxs-lookup"><span data-stu-id="a99ca-109">[in] A managed object pointer to the field name.</span></span>  
  
 `pValue`  
 <span data-ttu-id="a99ca-110">[out]フィールドの値。</span><span class="sxs-lookup"><span data-stu-id="a99ca-110">[out] The field value.</span></span> <span data-ttu-id="a99ca-111">このパラメーターには、null を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a99ca-111">This parameter can be null.</span></span>  
  
 `pOffset`  
 <span data-ttu-id="a99ca-112">[out]オフセット`objAddr`フィールドにします。</span><span class="sxs-lookup"><span data-stu-id="a99ca-112">[out] The offset from `objAddr` to the field.</span></span> <span data-ttu-id="a99ca-113">このパラメーターには、null を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a99ca-113">This parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a99ca-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="a99ca-114">Remarks</span></span>  
 <span data-ttu-id="a99ca-115">オフセットが 0 の場合は、オフセットは書き込まれません。</span><span class="sxs-lookup"><span data-stu-id="a99ca-115">If the offset is 0, no offset is written.</span></span>  
  
 <span data-ttu-id="a99ca-116">ないマネージ コードのスレッドで現在のコンテキストの場合、関数は、0xa0 の施設の値と 0x1000 のエラー コードをマネージを返します。</span><span class="sxs-lookup"><span data-stu-id="a99ca-116">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a99ca-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="a99ca-117">Requirements</span></span>  
 <span data-ttu-id="a99ca-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a99ca-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a99ca-119">**ヘッダー:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="a99ca-119">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="a99ca-120">**.NET framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a99ca-120">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a99ca-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="a99ca-121">See also</span></span>

- [<span data-ttu-id="a99ca-122">デバッグ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="a99ca-122">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
