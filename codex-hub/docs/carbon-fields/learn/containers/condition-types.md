# Condition Types

## `post_meta` conditions

| Name                 | Description                                                                                                                           |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| `'post_format'`      | Check against the post format. Use a blank string as the value to test if the post has no format assigned.                            |
| `'post_id'`          | Check against the post id.                                                                                                            |
| `'post_level'`       | Check against the post level in the hierarchy. Levels start from 1.                                                                   |
| `'post_parent_id'`   | Check against the post's parent id.                                                                                                   |
| `'post_ancestor_id'` | Check against the post's ancestors.                                                                                                   |
| `'post_template'`    | Check against the post's template filename. Pass `default` as the value to test against the default page template.                    |
| `'post_term'`        | Check against the post's terms. The expected value must be a term descriptor (see below).  `CUSTOM` callable is passed the post's id. |
| `'post_type'`        | Check against the post's type.                                                                                                        |

```php
// Display container on Books CPT
Container::make( 'post_meta', __( 'Book Data' ) )
	->where( 'post_type', '=', 'crb_book' )
	->add_fields( array( .. ) );

// Display container on page that uses the template `templates/homepage.php`
Container::make( 'post_meta', __( 'Homepage Settings' ) )
	->where( 'post_type', '=', 'page' )
	->where( 'post_template', '=', 'templates/homepage.php' )
	->add_fields( array( .. ) );
```

## `term_meta` conditions

| Name              | Description                                                                                                                           |
|-------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| `'term'`          | Check against the term according to the supplied term descriptor.  `CUSTOM` callable is passed the term's id.                         |
| `'term_level'`    | Check against the term's level in the hierarchy.                                                                                      |
| `'term_parent'`   | Check against the term's parent.                                                                                                      |
| `'term_ancestor'` | Check against the term's ancestors.                                                                                                   |
| `'term_taxonomy'` | Check against the term's taxonomy.                                                                                                    |

```php
// Display container on Book Category taxonomy
Container::make( 'term_meta', __( 'Book Category Data' ) )
	->where( 'term_taxonomy', '=', 'crb_book_category' )
	->add_fields( array( .. ) );
```

## `user_meta` conditions

| Name                | Description                                                                                                                           |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| `'user_capability'` | Check against the user's capabilities. `CUSTOM` callable is passed the user's id.                                                     |
| `'user_id'`         | Check against the user's id.                                                                                                          |
| `'user_role'`       | Check against the user's role. `CUSTOM` callable is passed an array of the user's roles.                                              |

```php
// Display container on for Administrators only
Container::make( 'user_meta', __( 'Administrator' ) )
	->where( 'user_role', '=', 'administrator' )
	->add_fields( array( .. ) );
```

## `theme_options` conditions

| Name         | Description                                                                                                                           |
|--------------|---------------------------------------------------------------------------------------------------------------------------------------|
| `'blog_id'`  | Check against the current blog's id                                                                                                   |

## Generally available conditions

The below conditions are applicable to any container and depend on the current user 

| Name                        | Description                                                                                                                           |
|-----------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| `'current_user_capability'` | Check against the current user's capabilities.  `CUSTOM` callable is passed the current user's id.                                    |
| `'current_user_id'`         | Check against the current user's id.                                                                                                  |
| `'current_user_role'`       | Check against the current user's role.  `CUSTOM` callable is passed an array of all current user's roles.                             |

```php
// Display theme options page to users who have the 'manage_options' capability
Container::make( 'theme_options', __( 'Theme Options' ) )
	->where( 'current_user_capability', '=', 'manage_options' )
	->add_fields( array( .. ) )
```

## Term Descriptors

Term-related conditions expect that you supply them with a term descriptor as the value (an array of term descriptors for the `IN` and `NOT IN` operators).  
A term descriptor is an array which has the following keys:

| Key        | Description                     |
|------------|---------------------------------|
| `field`    | The term field to compare with. |
| `value`    | The value for the term field.   |
| `taxonomy` | The taxonomy of the term.       |

## Example usage

```php
Container::make( 'post_meta', 'Custom Data' )
    ->where( 'post_term', '=', array(
        'field' => 'slug',
        'value' => 'featured',
        'taxonomy' => 'category',
    ) )
```

More information on these values can be found in the documentation of the [`get_term_by()`](https://developer.wordpress.org/reference/functions/get_term_by/) function in the WordPress Code Reference (the three keys here are identical to the first three arguments of this function).
