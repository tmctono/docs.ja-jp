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
ms.openlocfilehash: 0cf7b15392c90694db659f6faff6feecbef65466
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008335"
---
# <a name="iceegengetsectioncreate-method"></a><span data-ttu-id="bac59-102">ICeeGen::GetSectionCreate メソッド</span><span class="sxs-lookup"><span data-stu-id="bac59-102">ICeeGen::GetSectionCreate Method</span></span>
<span data-ttu-id="bac59-103">指定された名前とフラグ値を使用して、コードセクションを生成して取得します。</span><span class="sxs-lookup"><span data-stu-id="bac59-103">Generates and gets a code section using the specified name and flag values.</span></span>  
  
 <span data-ttu-id="bac59-104">このメソッドは互換性のために残されています。使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="bac59-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bac59-105">構文</span><span class="sxs-lookup"><span data-stu-id="bac59-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bac59-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bac59-106">Parameters</span></span>  
 `name`  
 <span data-ttu-id="bac59-107">から作成するセクションの名前を指定する文字列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="bac59-107">[in] A pointer to a string that specifies the name of the section to be created.</span></span>  
  
 `flags`  
 <span data-ttu-id="bac59-108">からオプションを指定するフラグ。</span><span class="sxs-lookup"><span data-stu-id="bac59-108">[in] Flags that specify options.</span></span>  
  
 `section`  
 <span data-ttu-id="bac59-109">入出力新しく作成されたコードセクションへのポインター。</span><span class="sxs-lookup"><span data-stu-id="bac59-109">[out] A pointer to the newly created code section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bac59-110">コメント</span><span class="sxs-lookup"><span data-stu-id="bac59-110">Remarks</span></span>  
 <span data-ttu-id="bac59-111">`GetSectionCreate`他のメソッドによって処理されない特殊なセクション要件がある場合にのみ、を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="bac59-111">Call `GetSectionCreate` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bac59-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="bac59-112">Requirements</span></span>  
 <span data-ttu-id="bac59-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bac59-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bac59-114">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="bac59-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bac59-115">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="bac59-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bac59-116">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bac59-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bac59-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="bac59-117">See also</span></span>

- [<span data-ttu-id="bac59-118">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bac59-118">ICeeGen Interface</span></span>](iceegen-interface.md)
