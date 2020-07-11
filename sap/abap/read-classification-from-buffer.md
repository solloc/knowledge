# Read classification from buffer

## Close classification of currently active object

```text
CALL FUNCTION 'CLO0_DDB_OBJ_VALUATION_CLOSE'
  EXCEPTIONS 
    error_at_tmp_save = 1
    OTHERS            = 2.
```

## Open classification of desired object

```text
CALL FUNCTION 'CLO0_DDB_OBJ_VALUATION_OPEN'
  EXPORTING 
*   CHANGE_NUMBER_IMP            = 
    classtype_imp                = '017'
    class_imp                    = 'Z_CENIT'
*   DATE_OF_CHANGE_IMP           = SY-DATUM 
*   DISPLAY_MODUS                = ' ' 
*   MTART_IMP                    = 
    object_imp                   = lv_object
    obj_structure_imp            = 'DRAW'
    show_all_values              = 'X'
*   OBTAB_IMP                    = 
*   LANGUAGE_IMP                 = SY-LANGU 
*   OVERRULE_UPARAM_IMP          = ' ' 
*   USER_PARAM_IMP               = 
*   FRAME_TEXT_NEW               = 
*   NO_LOCK                      = ' ' 
*   I_LOAD_CUSTOMIZING           = ' ' 
*   I_TABS_ACTIVE                = ' ' 
*   READONLY_CTMS                = ' ' 
*   I_CHECK_SYDATE               = ' ' 
* IMPORTING 
*   CUOBJ_EXP                    = 
EXCEPTIONS 
    invalid_classcat             = 1
    class_status_not_valid       = 2 
    class_not_found              = 3
    foreign_lock                 = 4
    system_failure               = 5
    change_nr_not_exist          = 6
" twice others... 
    no_authority                 = 8
    OTHERS                       = 9.
```

## Read desired characteristics \(optional\)

```text
CALL FUNCTION 'CTMS_DDB_HAS_CHARACTERISTICS'
  EXPORTING 
*   QUERY_MODE               = ' ' 
*   REQUIRED                 = 'X' 
*   OPTIONAL                 = 'X' 
*   INHERITED_ONLY           = ' ' 
*   ASSIGNED                 = 'X' 
    unassigned               = ' '
*   INHERITED_EXCLUDING      = ' ' 
*   ALLOWED                  = ' ' 
*   EXCLUDED                 = ' ' 
*   INCONSISTENT             = ' ' 
*   SORTED_BY_CLASS          = ' ' 
*   CONSIDER_AUTHORITY       = ' ' 
*   CONSIDER_SELCOND         = ' ' 
  TABLES 
    exp_characteristics      = lt_char
  EXCEPTIONS 
    not_found                = 1
    no_characteristic_in_ddb = 2
    OTHERS                   = 3.
```

## Read characteristic values

```text
CALL FUNCTION 'CTMS_DDB_HAS_VALUES'
  EXPORTING 
    assigned_values      = 'X' 
    allowed_values       = ' ' 
*   VALID_VALUES         = ' ' 
*   INCONSISTENT_VALUES  = ' ' 
*   FIRST_ASSIGNED_VALUE = ' ' 
*   DEFAULT_VALUES       = ' ' 
*   INCL_AUTHOR          = ' ' 
*   AUTHORITY_DISPLAY    = ' ' 
  TABLES 
    imp_characteristics  = lt_char
    exp_values           = lt_value
  EXCEPTIONS 
    not_found            = 1
    OTHERS               = 2. 
IF sy-subrc <> 0.
* Implement suitable error handling here
ENDIF.
```

## Close classification of currently active object

```text
CALL FUNCTION 'CLO0_DDB_OBJ_VALUATION_CLOSE'
  EXCEPTIONS 
    error_at_tmp_save = 1
    OTHERS            = 2.
```

