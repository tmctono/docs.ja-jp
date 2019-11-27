---
title: ICeeGen::GetIlSection メソッド
ms.date: 03/30/2017
api_name:
- ICeeGen.GetIlSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetIlSection
helpviewer_keywords:
- GetIlSection method [.NET Framework metadata]
- ICeeGen::GetIlSection method [.NET Framework metadata]
ms.assetid: 6f2db2ca-203f-4ac3-9530-208642ca385e
topic_type:
- apiref
ms.openlocfilehash: 7ef944fd06d07dc8c4e49061a5e72d8acc4d0465
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436351"
---
# <a name="iceegengetilsection-method"></a><span data-ttu-id="42bc4-102">ICeeGen::GetIlSection メソッド</span><span class="sxs-lookup"><span data-stu-id="42bc4-102">ICeeGen::GetIlSection Method</span></span>
<span data-ttu-id="42bc4-103">指定したハンドルによって参照される中間言語コードベースのセクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="42bc4-103">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="42bc4-104">このメソッドは互換性のために残されています。使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="42bc4-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42bc4-105">構文</span><span class="sxs-lookup"><span data-stu-id="42bc4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetIlSection (  
    [in] HCEESECTION  *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42bc4-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="42bc4-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="42bc4-107">から取得するセクションへのハンドル。</span><span class="sxs-lookup"><span data-stu-id="42bc4-107">[in] The handle to the section to get.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42bc4-108">要件</span><span class="sxs-lookup"><span data-stu-id="42bc4-108">Requirements</span></span>  
 <span data-ttu-id="42bc4-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42bc4-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42bc4-110">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="42bc4-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="42bc4-111">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="42bc4-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="42bc4-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42bc4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42bc4-113">参照</span><span class="sxs-lookup"><span data-stu-id="42bc4-113">See also</span></span>

- [<span data-ttu-id="42bc4-114">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="42bc4-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
