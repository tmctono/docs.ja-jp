---
title: GetCurrentApartmentType 関数 (アンマネージ API リファレンス)
description: GetCurrentApartmentType 関数は、呼び出し元を実行しているアパートメントの種類を取得します。
ms.date: 11/06/2017
api_name:
- GetCurrentApartmentType
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetCurrentApartmentType
helpviewer_keywords:
- GetCurrentApartmentType function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 76c852ac81126895ea3a2e1b40473722c8445201
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746559"
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="03f19-103">GetCurrentApartmentType 関数</span><span class="sxs-lookup"><span data-stu-id="03f19-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="03f19-104">呼び出し元が実行されているアパートメントの種類が取得されます。</span><span class="sxs-lookup"><span data-stu-id="03f19-104">Retrieves the type of apartment in which the caller is executing.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="03f19-105">構文</span><span class="sxs-lookup"><span data-stu-id="03f19-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a><span data-ttu-id="03f19-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="03f19-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="03f19-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="03f19-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="03f19-108">[in]ポインター、 [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="03f19-108">[in] A pointer to an [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) instance.</span></span>

`aptType`  
<span data-ttu-id="03f19-109">[out]ポインター、 [APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype)呼び出し元のアパートメントを示す列挙値。</span><span class="sxs-lookup"><span data-stu-id="03f19-109">[out] A pointer to an [APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="03f19-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="03f19-110">Return value</span></span>

|<span data-ttu-id="03f19-111">定数</span><span class="sxs-lookup"><span data-stu-id="03f19-111">Constant</span></span>  |<span data-ttu-id="03f19-112">値</span><span class="sxs-lookup"><span data-stu-id="03f19-112">Value</span></span>  |<span data-ttu-id="03f19-113">説明</span><span class="sxs-lookup"><span data-stu-id="03f19-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="03f19-114">0</span><span class="sxs-lookup"><span data-stu-id="03f19-114">0</span></span> | <span data-ttu-id="03f19-115">関数が正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="03f19-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="03f19-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="03f19-116">0x80000008</span></span> | <span data-ttu-id="03f19-117">呼び出し元は、アパートメントで実行していません。</span><span class="sxs-lookup"><span data-stu-id="03f19-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="03f19-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="03f19-118">Remarks</span></span>

<span data-ttu-id="03f19-119">この関数の呼び出しをラップする、 [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype)メソッド。</span><span class="sxs-lookup"><span data-stu-id="03f19-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="03f19-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="03f19-120">Requirements</span></span>  
 <span data-ttu-id="03f19-121">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="03f19-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03f19-122">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="03f19-122">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="03f19-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="03f19-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03f19-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="03f19-124">See also</span></span>

- [<span data-ttu-id="03f19-125">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="03f19-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
