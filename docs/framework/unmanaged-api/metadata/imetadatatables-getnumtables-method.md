---
title: IMetaDataTables::GetNumTables メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNumTables
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNumTables
helpviewer_keywords:
- GetNumTables method [.NET Framework metadata]
- IMetaDataTables::GetNumTables method [.NET Framework metadata]
ms.assetid: 8196f2a3-bbf2-45d3-a6cd-74502c356644
topic_type:
- apiref
ms.openlocfilehash: df02def0c14beb4e9ffd1b9260002767586a59b5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490199"
---
# <a name="imetadatatablesgetnumtables-method"></a><span data-ttu-id="28798-102">IMetaDataTables::GetNumTables メソッド</span><span class="sxs-lookup"><span data-stu-id="28798-102">IMetaDataTables::GetNumTables Method</span></span>
<span data-ttu-id="28798-103">現在のインスタンスのスコープ内にあるテーブルの数を取得し `IMetaDataTables` ます。</span><span class="sxs-lookup"><span data-stu-id="28798-103">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28798-104">構文</span><span class="sxs-lookup"><span data-stu-id="28798-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNumTables (  
    [out]  ULONG   *pcTables  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28798-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="28798-105">Parameters</span></span>  
 `pcTables`  
 <span data-ttu-id="28798-106">入出力現在のインスタンススコープ内にあるテーブルの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="28798-106">[out] A pointer to the number of tables in the current instance scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28798-107">要件</span><span class="sxs-lookup"><span data-stu-id="28798-107">Requirements</span></span>  
 <span data-ttu-id="28798-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28798-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28798-109">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="28798-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="28798-110">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="28798-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="28798-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28798-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28798-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="28798-112">See also</span></span>

- [<span data-ttu-id="28798-113">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="28798-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="28798-114">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="28798-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
