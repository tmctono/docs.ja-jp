---
title: ICeeGen::GetSectionCreate メソッド
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionCreate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionCreate
helpviewer_keywords:
- ICeeGen::GetSectionCreate method [.NET Framework metadata]
- GetSectionCreate method [.NET Framework metadata]
ms.assetid: 154b2460-59ce-4874-a9f2-1b3353486ac5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9768dfd43b6b60df1660c48cb6d6f498b049e256
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103312"
---
# <a name="iceegengetsectioncreate-method"></a><span data-ttu-id="66bb1-102">ICeeGen::GetSectionCreate メソッド</span><span class="sxs-lookup"><span data-stu-id="66bb1-102">ICeeGen::GetSectionCreate Method</span></span>
<span data-ttu-id="66bb1-103">生成し、指定した名前とフラグの値を使用してコードのセクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="66bb1-103">Generates and gets a code section using the specified name and flag values.</span></span>  
  
 <span data-ttu-id="66bb1-104">このメソッドは廃止され、使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66bb1-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66bb1-105">構文</span><span class="sxs-lookup"><span data-stu-id="66bb1-105">Syntax</span></span>  
  
```  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66bb1-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="66bb1-106">Parameters</span></span>  
 `name`  
 <span data-ttu-id="66bb1-107">[in]作成するセクションの名前を指定する文字列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="66bb1-107">[in] A pointer to a string that specifies the name of the section to be created.</span></span>  
  
 `flags`  
 <span data-ttu-id="66bb1-108">[in]オプションを指定するフラグ。</span><span class="sxs-lookup"><span data-stu-id="66bb1-108">[in] Flags that specify options.</span></span>  
  
 `section`  
 <span data-ttu-id="66bb1-109">[out]新しく作成されたコード セクションへのポインター。</span><span class="sxs-lookup"><span data-stu-id="66bb1-109">[out] A pointer to the newly created code section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66bb1-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="66bb1-110">Remarks</span></span>  
 <span data-ttu-id="66bb1-111">呼び出す`GetSectionCreate`別の方法で処理されない特別なセクションの要件がある場合にのみです。</span><span class="sxs-lookup"><span data-stu-id="66bb1-111">Call `GetSectionCreate` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66bb1-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="66bb1-112">Requirements</span></span>  
 <span data-ttu-id="66bb1-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="66bb1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66bb1-114">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="66bb1-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="66bb1-115">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="66bb1-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="66bb1-116">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="66bb1-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="66bb1-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="66bb1-117">See also</span></span>

- [<span data-ttu-id="66bb1-118">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="66bb1-118">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
